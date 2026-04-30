package com.mintstreet.consent.action;

import java.io.ByteArrayInputStream;
import java.io.UnsupportedEncodingException;
import java.security.InvalidAlgorithmParameterException;
import java.security.InvalidKeyException;
import java.security.NoSuchAlgorithmException;
import java.security.spec.InvalidKeySpecException;
import java.util.ArrayList;
import java.util.List;

import javax.crypto.BadPaddingException;
import javax.crypto.IllegalBlockSizeException;
import javax.crypto.NoSuchPaddingException;

import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;
import org.apache.struts2.result.StreamResult;
import org.json.JSONException;
import org.json.JSONObject;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.HttpRequestMethodNotSupportedException;

import com.mintstreet.common.action.CommonLoanAction;
import com.mintstreet.common.service.CommonService;
import com.mintstreet.common.util.EncryptDecryptUtil;
import com.mintstreet.common.util.RequestUtil;
import com.mintstreet.consent.entity.PrivacyRequest;

public class PrivacyNoticeAction extends CommonLoanAction {
	  private static final long serialVersionUID = 1L;
	  
	  private static final Logger logger = LogManager.getLogger(PrivacyNoticeAction.class.getName());
	  
	  @Autowired
	  private CommonService commonService;
	  
	  public StreamResult storePrivacyNotice() throws JSONException, HttpRequestMethodNotSupportedException, InvalidKeyException, NoSuchPaddingException, 
	  			NoSuchAlgorithmException, InvalidAlgorithmParameterException, BadPaddingException, IllegalBlockSizeException, InvalidKeySpecException, 
	  			UnsupportedEncodingException {
		  
	    StringBuilder str = new StringBuilder();
	    //String correlationId = UUID.randomUUID().toString();
	    
	    str = str.append("{");
	    if(RequestUtil.getServletRequest().getMethod().equalsIgnoreCase("POST")) {
	    try {
	    		
	    	//TODO need to decrypt request
	    	
	    	//need to do preValidation
	    	List<String> errors = validateRequestAPI(privacyRequest);
	    	//if length of errors is > 0, then status code -> 204 and send response
	    	
	    	//400 validation 
	    	if(!errors.isEmpty()) {
	    		JSONObject jsonObj = buildJsonResponse(false, 400, errors, null, null);
	    		str.append(jsonObj.toString());
	    	} else {		//TODO 200 status code to be sent at end 
	    		//200 success 
	    		JSONObject body=new JSONObject();
	    		body.put("ack", "value");
	    		body.put("locale", "value");
	    		body.put("version", "value");
	    		JSONObject jsonObj=buildJsonResponse(true, 200, null, null , body); //TODO change 3rd parameter of "Success"
	    	}
	    	
	    	
	    	//need to validate request
	    	if(!validateRequest()) {	//TODO use only one method for validation and set error message from the same method.
	    		String m = getMessage();
	    		JSONObject jsonObj = new JSONObject();
	    		jsonObj.put("reference number", "");	// TODO set proper response fields
	            jsonObj.put("status", "FAILED");
	            jsonObj.put("errors", m);
	            str.append(jsonObj.toString());
	    		str.append("}");
	    		String res = encryptData(str.toString(), EncryptDecryptUtil.decrypt("xyzneed to encrypt request "));
	    		logger.info("UploadLead. java :: LNO: 101 encrypted responses is : " + res);
	    	    return new StreamResult(new ByteArrayInputStream(res.toString().getBytes()));
	    	}
	    	    
	   // if (((UploadBean)this.quickLead.get(0)).getSMS_Content().contains("MISSED_CALL")) {} else {} 
		    } catch (JSONException e) {
		        this.json.put("error", "1");
		        logger.info("UploadLead. java :: LNO: 417 : Exception Caught " + e);
		        JSONObject jsonObj=buildJsonResponse(false, 500, null, null, null); ////TODO change 3rd parameter of "Internal Server Error"
		        str.append(jsonObj.toString());
		     } catch (Exception e) {
		      this.json.put("error", "1");
		      logger.info("UploadLead. java :: LNO: 420 : Exception Caught " + e);
		    }
	    } else {
	    	logger.info("UploadLead. java :: Got HTTP request of type " + RequestUtil.getServletRequest().getMethod());
	    	
	    	  /*JSONObject jsonObj = new JSONObject();
	    	  jsonObj.put("success",false);
              jsonObj.put("statusCode", 405);
              jsonObj.put("messages", "Method not allowed.");
              jsonObj.put("errors", "null");
              jsonObj.put("body","null");
              jsonObj.putOpt("timestamp", "localDate");*/
	    	
	    	JSONObject jsonObj=buildJsonResponse(false,405,null,null,null);////TODO change 3rd parameter of "Method not allowed"
	    	
              str.append(jsonObj.toString());
	    	 
       
	    	throw new HttpRequestMethodNotSupportedException("POST");
	    }
	    str.append("}");
	    //String res = encryptData(str.toString(), EncryptDecryptUtil.decrypt(secreteKey));
	    //logger.info("UploadLead. java :: LNO: 428 encrypted responses is : " + res);
	    return new StreamResult(new ByteArrayInputStream("abc".toString().getBytes()));
	  }
	    
	  private String encryptData(String string, String decrypt) {
		// TODO Auto-generated method stub
		return null;
	  }


	  private boolean validateRequest() {
		
		  if (!(privacyRequest.getTouchPointId().length()>=1 && privacyRequest.getTouchPointId().length()<=10)) {
			  logger.info("privacyRequest. java :: LNO: 457 invalid touch Point ID");
			  return false;
		}
		if (!(privacyRequest.getPrivacyNotice().length() >= 3
				&& privacyRequest.getPrivacyNotice().length() <= 64000)) {
			logger.info("privacyRequest. java :: LNO: 461 invalid Privacy Notice");

			return false;
		}
		if (!(privacyRequest.getLocale().length() >= 3 && privacyRequest.getLocale().length() <= 3)) {
			logger.info("privacyRequest. java :: LNO: 467 invalid Reference Number");

			return false;
		}
		if (!(privacyRequest.getVersion().toString().length() >= 1
				&& privacyRequest.getVersion().toString().length() <= 999999)) {
			logger.info("privacyRequest. java :: LNO: 471 invalid Version");

			return false;
		}
		if (!privacyRequest.getTimestamp().matches(
				"^\\\\d{4}-(0[1-9]|1[0-2])-(0[1-9]|[12]\\\\d|3[01])T([01]\\\\d|2[0-3]):[0-5]\\\\d:[0-5]\\\\dZ$")) {
			logger.info("privacyRequest. java :: LNO: 477 invalid time stamp");

			return false;
		}
		if (!privacyRequest.getCorrelationId()
				.matches("^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$")) {
			logger.info("privacyRequest. java :: LNO: 482 invalid correlation Id");

			return false;
		}
		return true;
		}
		
		private String getMessage() {
				if (!(privacyRequest.getTouchPointId().length()>=1 && privacyRequest.getTouchPointId().length()<=10)) {
					logger.info("privacyRequest. java :: LNO: 457 invalid touch Point ID");
					privacyRequest.toString();
					return "invalid touch Point ID";
				}
				if (!(privacyRequest.getPrivacyNotice().length()>=3 && privacyRequest.getPrivacyNotice().length()<=64000)) {
					logger.info("privacyRequest. java :: LNO: 461 invalid Privacy Notice");

					return "invalid Privacy Notice";
				}
				if (!(privacyRequest.getLocale().length() ==3)) {
					logger.info("privacyRequest. java :: LNO: 467 invalid locale ");

					return "invalid locale ";
				}
				if (!(privacyRequest.getVersion().toString().length() >=1 && privacyRequest.getVersion().toString().length() <=999999)) {
					logger.info("privacyRequest. java :: LNO: 471 invalid Version");

					return "invalid Version Number";
				}
				if (!privacyRequest.getTimestamp().matches("^\\\\d{4}-(0[1-9]|1[0-2])-(0[1-9]|[12]\\\\d|3[01])T([01]\\\\d|2[0-3]):[0-5]\\\\d:[0-5]\\\\dZ$")) {
					logger.info("privacyRequest. java :: LNO: 477 invalid time stamp");

					return "invalid time stamp";
				}
				if (!privacyRequest.getCorrelationId().matches("^[0-9a-fA-F]{8}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{4}-[0-9a-fA-F]{12}$")) {
					logger.info("privacyRequest. java :: LNO: 482 invalid correlation Id");

					return "invalid correlation Id";
				}
		  
			return "";
			
		}
		
		private JSONObject buildJsonResponse(Boolean status, Integer statusCode, List<String> messsage, JSONObject errors, JSONObject body) throws JSONException {

	         JSONObject obj=new JSONObject();
	         obj.put("success",status);
	         obj.put("statusCode",statusCode);
	         obj.put("messages", messsage);
	         obj.put("errors", errors);
	         obj.put("body", body);
	         obj.put("timestamp"," java.text.SimpleDateFormat('yyyy-mm-dd'T'HH:mm:ss')");//TODO remove hardcoded value
	         obj.put("correlationId", "asdjaf"); //TODO add value later
	         
	         return obj;
		}

	    private List<String> validateRequestAPI(PrivacyRequest privacyRequest) {
	    	
	    	List<String> errors = new ArrayList<>();
	    	
	    	if(privacyRequest.getTouchPointId().isEmpty() ||  privacyRequest.getTouchPointId()==null)
	    		errors.add("touchPointId is Mandatory");
	    	
	    	if(privacyRequest.getPrivacyNotice().isEmpty() || privacyRequest.getPrivacyNotice()==null)
	    		errors.add("privacyNotice is Mandatory");
	    	
	    	if(privacyRequest.getLocale().isEmpty() || privacyRequest.getLocale()==null)
	    		errors.add("locale is mandatory");
	    	
	    	if(privacyRequest.getVersion().toString().isEmpty() || privacyRequest.getVersion()==null)
	    		errors.add("version is mandatory");
	    	
	    	if(privacyRequest.getTimestamp().isEmpty() || privacyRequest.getTimestamp()==null)
	    		errors.add("timestamp is mandatory");
	    	
	    	if(privacyRequest.getCorrelationId().isEmpty() || privacyRequest.getCorrelationId()==null)
               errors.add("correlationID is mandatory");
	    	
			return errors;
	    	
	    }
	    
}
