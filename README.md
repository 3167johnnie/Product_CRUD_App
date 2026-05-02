<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="http://java.sun.com/xml/ns/javaee" xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd" version="2.5">
  <display-name>www.sbi.co.in</display-name>
  <listener>
        <listener-class>org.apache.logging.log4j.web.Log4jServletContextListener</listener-class>
    </listener>
  <listener>
    <listener-class>
			org.springframework.web.context.ContextLoaderListener
	</listener-class>
  </listener>
  <context-param>
    <param-name>contextConfigLocation</param-name>
    <param-value>/WEB-INF/applicationContext.xml</param-value>
  </context-param>
   <filter>
        <filter-name>log4jServletFilter</filter-name>
        <filter-class>org.apache.logging.log4j.web.Log4jServletFilter</filter-class>
    </filter>
   <filter>
    <filter-name>xssFilter</filter-name>
	<filter-class>
			com.mintstreet.common.security.XSSFilter</filter-class>
  </filter>
  <filter>
    <filter-name>cacheControlFilter</filter-name>
	<filter-class>
			com.mintstreet.common.security.CacheControlFilter</filter-class>
  </filter>
   <filter-mapping>
        <filter-name>log4jServletFilter</filter-name>
        <url-pattern>/*</url-pattern>
        <dispatcher>REQUEST</dispatcher>
        <dispatcher>FORWARD</dispatcher>
        <dispatcher>INCLUDE</dispatcher>
        <dispatcher>ERROR</dispatcher>
        <!-- <dispatcher>ASYNC</dispatcher> --><!-- Servlet 3.0 w/ disabled auto-initialization only; not supported in 2.5 -->
    </filter-mapping>
  <filter-mapping>
    <filter-name>xssFilter</filter-name>
    <url-pattern>/*</url-pattern>
  </filter-mapping>
  <filter-mapping>
    <filter-name>cacheControlFilter</filter-name>
    <url-pattern>/*</url-pattern>
  </filter-mapping>
  <filter>
    <filter-name>jpaFilter</filter-name>
    <filter-class>
			org.springframework.orm.jpa.support.OpenEntityManagerInViewFilter</filter-class>
  </filter>
  <filter-mapping>
    <filter-name>jpaFilter</filter-name>
    <url-pattern>/*</url-pattern>
  </filter-mapping>
  <filter>
    <filter-name>struts2</filter-name>
    <filter-class>
			org.apache.struts2.dispatcher.filter.StrutsPrepareAndExecuteFilter
	</filter-class>
  </filter>
  <filter-mapping>
    <filter-name>struts2</filter-name>
    <url-pattern>/</url-pattern>
	<url-pattern>/changelanguage</url-pattern>
	<url-pattern>/home-faq</url-pattern>
	<url-pattern>/contact-us</url-pattern>
	<url-pattern>/privacy-statement</url-pattern>
	<url-pattern>/disclosure-statement</url-pattern>
	<url-pattern>/term-condition</url-pattern>
	<url-pattern>/under-maintainance</url-pattern>
	<url-pattern>/home</url-pattern>
	<url-pattern>/residancetypeonchange</url-pattern>
	<url-pattern>/citybystateid</url-pattern>
	<url-pattern>/getCitiesForHomeLoan</url-pattern>
	<url-pattern>/getDistrictByStateId</url-pattern>
	<url-pattern>/pinCodeByCityId</url-pattern>
	<url-pattern>/pinCodeByDistrictId</url-pattern>
	<url-pattern>/disticByStateid</url-pattern>
	<url-pattern>/branchByStateId</url-pattern>
	<url-pattern>/branchByDistrictId</url-pattern>
	<url-pattern>/branchByCityId</url-pattern>
	<url-pattern>/localityordistrictbystateandcityid</url-pattern>
	<url-pattern>/getallbank</url-pattern>
	<url-pattern>/loanPurposeByParentId</url-pattern>
	<url-pattern>/getAllEmployer</url-pattern>
	<url-pattern>/getAllBranchName</url-pattern>
	<url-pattern>/getAllEmployerForPL</url-pattern>
	<url-pattern>/getAllEmployerForXpressCreditIT</url-pattern>
	<url-pattern>/getAllBuilder</url-pattern>
	<url-pattern>/getPreownedCarDealer</url-pattern>
	<url-pattern>/getRequestConfigByLoanType</url-pattern>
	<url-pattern>/getTypeOfSalaryPackage</url-pattern>
	<url-pattern>/getTypeOfSalaryPackageRank</url-pattern>
	<url-pattern>/flexi-pay-emis</url-pattern>
	<url-pattern>/campaign-lead</url-pattern>
	<url-pattern>/privacy-notice</url-pattern>
	<url-pattern>/sms-consent</url-pattern>
	<url-pattern>/infronics-Lead</url-pattern>
	<url-pattern>/ivrs-otp</url-pattern>
	<url-pattern>/mingle-lead</url-pattern>
	<url-pattern>/ios-url</url-pattern>
	<url-pattern>/home-about-us</url-pattern>
	<url-pattern>/agri-loan-actions</url-pattern>
	<!-- <url-pattern>/agri-loan</url-pattern> -->
	<url-pattern>/agri-loan-dsr</url-pattern>
	<url-pattern>/agriMake</url-pattern>
	<url-pattern>/agriModel</url-pattern>
	<url-pattern>/application-status</url-pattern>
	<url-pattern>/getapplicationtrack</url-pattern>
	<url-pattern>/auto-loan</url-pattern>
	<url-pattern>/auto-loan-dsr</url-pattern>
	<url-pattern>/bikeCompanyByBikeTypeId</url-pattern>
	<url-pattern>/bikeModelByCompanyId</url-pattern>
	<url-pattern>/bikeVariantByBikeModuleId</url-pattern>
	<url-pattern>/carVariantByCarModuleId</url-pattern>
	<url-pattern>/carModelByCompanyId</url-pattern>
	<url-pattern>/occupationByEmployementTypeID</url-pattern>
	<url-pattern>/exshowRoomPriceByCarVariantId</url-pattern>
	<url-pattern>/getDealerByCompanyId</url-pattern>
	<url-pattern>/initiateProcess</url-pattern>
	<url-pattern>/sendOTP</url-pattern>
	<url-pattern>/reSendOTP</url-pattern>
	<url-pattern>/verifyOTP</url-pattern>
	<url-pattern>/getLoanQuote</url-pattern>
	<url-pattern>/getSliderQuote</url-pattern>
	<url-pattern>/applyApplication</url-pattern>
	<url-pattern>/finalFormSubmit</url-pattern>
	<url-pattern>/downloadPdf</url-pattern>
	<url-pattern>/submitAppTrack</url-pattern>
	<url-pattern>/call-rule-engine</url-pattern>
	<url-pattern>/call-pdf-engine</url-pattern>
	<url-pattern>/call-nsdl-engine</url-pattern>
	<url-pattern>/getCallbackMasters</url-pattern>
	<url-pattern>/call-intial-token</url-pattern>
	<url-pattern>/getMasters</url-pattern>
	<url-pattern>/getModel</url-pattern>
	<url-pattern>/getVariant</url-pattern>
	<url-pattern>/getCity</url-pattern>
	<url-pattern>/getDistrict</url-pattern>
	<url-pattern>/getBranches</url-pattern>
	<url-pattern>/getAllStates</url-pattern>
	<url-pattern>/getEmployerList</url-pattern>
	<url-pattern>/finalAppointment</url-pattern>
	<url-pattern>/getCallBack</url-pattern>
	<url-pattern>/reSendOTPCallBack</url-pattern>
	<url-pattern>/callBackVerifyOTP</url-pattern>
	<url-pattern>/getAppRefStatus</url-pattern>
	<url-pattern>/getDocuments</url-pattern>
	<url-pattern>/getCBSCall</url-pattern>
	<url-pattern>/resendOTPCBS</url-pattern>
	<url-pattern>/verifyOTPCBS</url-pattern>
	<url-pattern>/setDeviceInfo</url-pattern>
	<url-pattern>/encrypt</url-pattern>
	<url-pattern>/credit-card</url-pattern>
	<url-pattern>/credit-card-dsr</url-pattern>
	<url-pattern>/generate-missing-pdf</url-pattern>
	<url-pattern>/edvantage-loan</url-pattern>
	<url-pattern>/scholar-loan</url-pattern>
	<url-pattern>/education-loan-dsr</url-pattern>
	<url-pattern>/instituteByCourseType</url-pattern>
	<url-pattern>/instituteCategoryType</url-pattern>
	<url-pattern>/getAllCourseName</url-pattern>
	<url-pattern>/getAllInstituteName</url-pattern>
	<url-pattern>/getAllUniversity</url-pattern>
	<url-pattern>/initeducationloan</url-pattern>
	<url-pattern>/education-takeover-loan</url-pattern>
	<url-pattern>/instituteByCourseType</url-pattern>
	<url-pattern>/instituteCategoryType</url-pattern>
	<url-pattern>/getAllCourseName</url-pattern>
	<url-pattern>/getAllInstituteName</url-pattern>
	<url-pattern>/getAllUniversity</url-pattern>
	<url-pattern>/sbi-flipkart</url-pattern>
	<url-pattern>/check-eligibility</url-pattern>
	<url-pattern>/verify-Otp</url-pattern>
	<url-pattern>/resend-Otp</url-pattern>
	<url-pattern>/inithomeloan</url-pattern>
	<url-pattern>/home-loan</url-pattern>
	<url-pattern>/home-loan-dsr</url-pattern>
	<url-pattern>/getAllProject</url-pattern>
	<url-pattern>/inithomeloan</url-pattern>
	<url-pattern>/home-top-up-loan</url-pattern>
	<url-pattern>/getAllProject</url-pattern>
	<url-pattern>/initpensionloan</url-pattern>
	<url-pattern>/pension-loan</url-pattern>
	<url-pattern>/getInstituteCategoryByName</url-pattern>
	<url-pattern>/getEmployerByName</url-pattern>
	<url-pattern>/personal-loan-actions</url-pattern>
	<url-pattern>/personal-loan</url-pattern>
	<url-pattern>/personal-loan-dsr</url-pattern>
	<url-pattern>/pension-loan</url-pattern>
	<url-pattern>/getInstituteCategoryByName</url-pattern>
	<url-pattern>/getInstituteCategoryByName</url-pattern>
	<url-pattern>/getEmployerByName</url-pattern>
	<url-pattern>/campaign-home</url-pattern>
	<url-pattern>/sbi-tata</url-pattern>
	<url-pattern>/confirm-Otp</url-pattern>
	<url-pattern>/resend-Otp</url-pattern>
	<url-pattern>/downloadSbiTataPdf</url-pattern>
	<url-pattern>/upload-vidya-lakshmi-loan</url-pattern>
	<url-pattern>/download-vidya-lakshmi-loan</url-pattern>
	<!-- <url-pattern>/vlp-file-list</url-pattern>
	<url-pattern>/vlp-get-file</url-pattern>
	<url-pattern>/vlp-status-report</url-pattern>
	<url-pattern>/vlp-status-upload</url-pattern>
	<url-pattern>/vlp-process-file</url-pattern> -->
	<url-pattern>/subDistrictByDistrictId</url-pattern>
	<url-pattern>/villageBysubdistrictId</url-pattern>
	<url-pattern>/uploadimage.action</url-pattern>
	<url-pattern>/Captcha/*</url-pattern>
	<url-pattern>/Captcha.jpg</url-pattern>
	<url-pattern>/SBI_LOS/rest</url-pattern>
	<url-pattern>/encrypt</url-pattern>
	<url-pattern>/decrypt</url-pattern>
	<url-pattern>/docUpload</url-pattern>
	<url-pattern>/getInstituteList</url-pattern>
	<url-pattern>/getAllProjects</url-pattern>
	<url-pattern>/quoteEmailData</url-pattern>
	<url-pattern>/getAgriState</url-pattern>
	<url-pattern>/getAgriDistrict</url-pattern>
	<url-pattern>/customer-feedback</url-pattern>
	<url-pattern>/customer-feedback-page</url-pattern>
	<url-pattern>/resend-Otp</url-pattern>
	<url-pattern>/customer-feedback-submit</url-pattern>
	<url-pattern>/getCardEmployerName</url-pattern>
	<url-pattern>/getAgriCityList</url-pattern>
	<url-pattern>/bulkUpload</url-pattern>
	<!-- url mappings for instant loans start -->
	<url-pattern>/pushNotifications</url-pattern>
	<url-pattern>/sendEmailAlerts</url-pattern>
	<url-pattern>/readIdspmCsv</url-pattern>
	<url-pattern>/readIdspmCsvOnDate</url-pattern>
	<url-pattern>/sendSmsAlerts</url-pattern>
	<url-pattern>/downloadIDSPMDump</url-pattern>
	<url-pattern>/sendEmailISDPMDump</url-pattern>
	
	<url-pattern>/callCreditVidyaService</url-pattern>
	<url-pattern>/callCreditVidyaBREService</url-pattern>
	
	<url-pattern>/getKeyAndServiceId</url-pattern>
	<url-pattern>/validateUserINB</url-pattern>
	<url-pattern>/validateUserATM</url-pattern>
	<url-pattern>/createLoanAccountInCBS</url-pattern>
	
	<url-pattern>/unsubscribeForNotifications</url-pattern>
	<url-pattern>/update-constants</url-pattern>
    <!-- url mappings for instant loans end -->
	<!-- Work for Campaign Loan start -->
	<url-pattern>/home-loan-callback</url-pattern>
	<url-pattern>/car-loan-callback</url-pattern>
	<url-pattern>/global-ed-callback</url-pattern>
	<url-pattern>/agri-loan-callback</url-pattern>
	<!-- Work for Campaign Loan end -->
	<url-pattern>/bidyalakhmi-loan</url-pattern>
	<url-pattern>/logout</url-pattern>
	<url-pattern>/get-feedback-url</url-pattern>
	<url-pattern>/getString</url-pattern>
	<url-pattern>/call-click2call-service</url-pattern>
	<url-pattern>/gold-loan</url-pattern>
	<url-pattern>/sendSmsAlertsByPk</url-pattern>
	<url-pattern>/quick-lead</url-pattern>
	<url-pattern>/cve</url-pattern>
	<url-pattern>/cve-loan-actions</url-pattern>
    <dispatcher>FORWARD</dispatcher>
    <dispatcher>REQUEST</dispatcher>
  </filter-mapping>
  <listener>
    <listener-class>
			com.mintstreet.common.session.SessionSendMailListener
	</listener-class>
  </listener>
  <servlet>
    <servlet-name>Captcha</servlet-name>
    <servlet-class>com.mintstreet.common.util.ImageCaptcha</servlet-class>
  </servlet>
  <servlet-mapping>
    <servlet-name>Captcha</servlet-name>
    <url-pattern>/Captcha.jpg</url-pattern>
  </servlet-mapping>
  <error-page>
    <error-code>404</error-code>
    <location>/app/common/error404.jsp</location>
  </error-page>
  <error-page>
    <error-code>500</error-code>
    <location>/app/common/error404.jsp</location>
  </error-page>
  <error-page>
    <error-code>502</error-code>
    <location>/app/common/error404.jsp</location>
  </error-page>
  <error-page>
    <error-code>503</error-code>
    <location>/app/common/error404.jsp</location>
  </error-page>
  <session-config>
    <session-timeout>10</session-timeout>
  </session-config>
  <welcome-file-list>
    <welcome-file>home</welcome-file>
  </welcome-file-list>
</web-app>



-------

struts.xml


<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE struts PUBLIC
 "-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
 "http://struts.apache.org/dtds/struts-2.0.dtd">
<struts>
	<constant name="struts.objectFactory" value="spring" />
	<constant name="struts.devMode" value="false" />
	<constant name="struts.ognl.allowStaticMethodAccess" value="true"/>
	<constant name="struts.multipart.maxSize" value="16777216"/>
	<include file="struts-interceptor.xml" />
	<package name="sbi" extends="sbi-interceptor">
		<default-action-ref name="home" />

		<global-results>
			<result name="home" type="redirect">/</result>
			<result name="originator" type="redirect">home</result>
			<result name="under-maintainance" type="redirect">under-maintainance</result>
			<result name="exception">/app/common/exception.jsp?mode=debug</result>
			<result name="404">/app/common/error404.jsp</result>
			<!-- <result name="error-action">/app/common/error404.jsp</result> -->
			<result name="applicationTrack" type="redirect">
				<param name="location">application-status</param>
				<param name="appReferencetIdEncrypted">${appReferencetIdEncrypted}</param>
				<param name="responseMessage">${responseMessage}</param>
			</result>
			<result name="applicationTrackNew" type="redirect">
				<param name="location">application-status</param>
				<param name="appReferencetIdEncrypted">${appReferencetIdEncrypted}</param>
				<param name="responseMessage">${responseMessage}</param>
			</result>
		</global-results>

		<global-exception-mappings>
			<exception-mapping exception="java.lang.Exception" result="exception" />
		</global-exception-mappings>
		<action name="uploadimage" method="upload" class="fileUploadAction">
			<interceptor-ref name="fileUpload">
				<param name="maximumSize">3145728</param>
				<param name="allowedTypes">
					image/pjpeg,image/jpeg,image/jpg,image/png,image/gif,application/pdf
				</param>
			</interceptor-ref>
			<interceptor-ref name="defaultFileUploadStack"></interceptor-ref>
		</action>
	</package>
	<include file="struts-generic-actions.xml"/>
	<include file="struts-common-loan.xml"/>
	<include file="struts-application-track-actions.xml"/>
	<include file="struts-home-loan-actions.xml"/>
	<include file="struts-home-topup-loan-actions.xml"/>
	<include file="struts-auto-loan-actions.xml"/>
	<include file="struts-education-loan-actions.xml"/>
	<include file="struts-personal-loan-actions.xml"/>	
	<include file="struts-vidya-lakshmi-loan-actions.xml"/>
	<include file="struts-cron-action.xml"/>
	<include file="struts-sbi-campaign.xml"/>
	<include file="struts-common-loan-web-service.xml"/>
	<include file="struts-agri-loan-actions.xml"/>
	<include file="struts-credit-card-actions.xml"></include>
	<include file="struts-flipkart-microsite.xml"/>
	<include file="struts-customer-feedback-action.xml"/>
	<include file="struts-instant-loan-action.xml"/>
	<include file="struts-campaign-callback.xml"/>
	<include file="struts-cve.xml"/>
</struts>




-----------------

struts-common-loan.xml


<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE struts PUBLIC
 "-//Apache Software Foundation//DTD Struts Configuration 2.0//EN"
 "http://struts.apache.org/dtds/struts-2.0.dtd">
 
 <!-- Home Loan action -->
 
 <struts>
 	<package name="common-loan-actions" extends="sbi">
 	
 		<!-- <action name="initloan" method="initLoan" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       	 	</result>
		</action> -->
		<action name="changelanguage" method="changeLanguage" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       	 	</result>
		</action>
		<action name="home-faq" method="homeFaq" class="commonLoanAction">
      		<result name="successOld">/app/common/homeFAQ.jsp</result>
      		<result name="success">/appNew/common/HomeFAQ.jsp</result>
      	</action>
		
		<action name="contact-us" method="contactUs" class="commonLoanAction">
      		<result name="successOld">/app/common/contactUs.jsp</result>
      		<result name="success">/appNew/common/ContactUs.jsp</result>
      	</action>
      	
      	<action name="under-maintainance" method="underMaintainance" class="commonLoanAction">
      		<result name="successOld">/app/common/home.jsp</result>
      		<result name="success">/appNew/common/Home.jsp</result>
      	</action>
      	
      	<action name="home" method="home" class="commonLoanAction">
      		<result name="successOld">/app/common/home.jsp</result>
      		<result name="success">/appNew/common/Home.jsp</result>
      		<result name="jsonResponsePage">/app/common/jsonResponsePage.jsp</result>
      	</action>
		
		<action name="residancetypeonchange" method="residanceTypeOnChange" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
      	</action>
		<action name="citybystateid" method="cityByStateId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="getCitiesForHomeLoan" method="getCitiesForHomeLoan" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="getDistrictByStateId" method="getDistrictByStateId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		<action name="pinCodeByCityId" method="pinCodeByCityId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="pinCodeByDistrictId" method="pinCodeByDistrictId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		<action name="disticByStateid" method="disticByStateid" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="branchByStateId" method="branchByStateId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		<action name="branchByDistrictId" method="branchByDistrictId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="branchByCityId" method="branchByCityId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<!-- <action name="localityByStateId" method="localityByStateId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action> -->
		
		<action name="localityordistrictbystateandcityid" method="localityOrDistrictByStateandCityId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		<action name="getallbank" method="getAllBank" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="loanPurposeByParentId" method="loanPurposeByParentId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="getAllEmployer" method="getAllEmployer" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="getAllBranchName" method="getAllBranchName" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="getAllEmployerForPL" method="getAllEmployerForPL" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		<action name="getAllEmployerForXpressCreditIT" method="getAllEmployerForXpressCreditIT" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="getAllBuilder" method="getAllBuilder" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="getPreownedCarDealer" method="getPreownedCarDealer" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<!-- <action name="uiFieldByParentId" method="uiFieldByParentId" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action> -->
		
		<action name="getRequestConfigByLoanType" method="getRequestConfigByLoanType" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>
		
		<action name="getTypeOfSalaryPackage" method="getTypeOfSalaryPackage" class="commonLoanAction">
			<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
		</action>

		<action name="encrypt" method="getEncrypt" class="commonLoanAction">
      		<result name="jsonResponsePage">/app/common/jsonResponsePage.jsp</result>
      	</action>
      	
		<action name="decrypt" method="getDecrypt" class="commonLoanAction">
      		<result name="jsonResponsePage">/app/common/jsonResponsePage.jsp</result>
      	</action>
      	
		<action name="sms-consent" method="getSmsCallBackUrlResponse" class="commonLoanAction">
      	
      	</action>
      	 <!-- 	<action name="flexi-pay-emis" method="getFlexiPayEmis" class="commonLoanAction">
      		<result name="jsonResponsePage">/app/common/jsonResponsePage.jsp</result>
      	</action> -->
      	
      	<action name="campaign-lead" method="quickUploadLead" class="uploadLead">
      		<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
       		<interceptor-ref name="defaultStack"></interceptor-ref>
       	 	<interceptor-ref name="json">
				<param name="enableSMD">true</param>
			</interceptor-ref>
      	</action>
      	<action name="privacy-notice" method="storePrivacyNotice" class="privacyNoticeAction">
      		<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
       		<interceptor-ref name="defaultStack"></interceptor-ref>
       	 	<interceptor-ref name="json">
				<param name="enableSMD">true</param>
			</interceptor-ref>
      	</action>
      	<action name="infronics-Lead" method="infronicsLead" class="infronicsLead">
      		<result name="success">/app/common/home.jsp</result>
      	</action>
      	<action name="ivrs-otp" method="getIvrsOtpCallBackUrlResponse" class="commonLoanAction">
      		<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
      	</action>
      	
      <!-- 	<action name="crm-serviceCall" method="crmLeadSave" class="commonLoanAction">
      		
      	</action>
      	 -->
      	<action name="mingle-lead" method="processMingleLead" class="mingleLead">
      		<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
       		<interceptor-ref name="defaultStack"></interceptor-ref>
       	 	<interceptor-ref name="json">
				<param name="enableSMD">true</param>
			</interceptor-ref>
      	</action>
      	<action name="home-about-us" method="homeAboutUs" class="commonLoanAction">
      		<result name="success">/appNew/common/HomeAboutUs.jsp</result>
      	</action>
      	<action name="ivrs-otp" method="getIvrsOtpCallBackUrlResponse" class="commonLoanAction">
      		<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
      	</action>
		<action name="logout" method="logout" class="commonLoanAction">
      		<result name="success">/app/common/jsonResponsePage.jsp</result>
      	</action>
      	<action name="update-constants" method="updateConstants" class="commonLoanAction">
      		<result name="jsonResponsePage">/app/common/jsonResponsePage.jsp</result>
      	</action>
      	<action name="getString" method="getSaltKey" class="commonLoanAction">
      		<result name="jsonResponsePage">/app/common/jsonResponsePage.jsp</result>
      	</action>
      	<action name="quick-lead" method="lmsQuickUploadLead" class="uploadLead">
      		<result name="success" type="json">
       	 		<param name="root">json</param>
       		</result>
       		<interceptor-ref name="defaultStack"></interceptor-ref>
       	 	<interceptor-ref name="json">
				<param name="enableSMD">true</param>
			</interceptor-ref>
      	</action>
	</package>
</struts>






---------------------

<beans xmlns="http://www.springframework.org/schema/beans"	xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:aop="http://www.springframework.org/schema/aop"	xmlns:context="http://www.springframework.org/schema/context" xmlns:tx="http://www.springframework.org/schema/tx" xsi:schemaLocation="http://www.springframework.org/schema/beans http://www.springframework.org/schema/beans/spring-beans-3.0.xsd http://www.springframework.org/schema/context http://www.springframework.org/schema/context/spring-context-3.0.xsd http://www.springframework.org/schema/tx http://www.springframework.org/schema/tx/spring-tx-3.0.xsd" default-lazy-init="true">

	<context:component-scan base-package="com.mintstreet" />
	<context:property-placeholder location="file:${catalina.home}/ocas_configuration/config.properties,file:${catalina.home}/ocas_configuration/Constants.properties" />
	<bean class="org.springframework.orm.jpa.support.PersistenceAnnotationBeanPostProcessor" />
	
	<!--- JPA transaction manager -->
	<bean id="entityManagerFactory" class="org.springframework.orm.jpa.LocalContainerEntityManagerFactoryBean">
		<property name="persistenceUnitName" value="punit" />
		<property name="dataSource" ref="dataSource" />
		<property name="jpaVendorAdapter">
			<bean class="org.springframework.orm.jpa.vendor.HibernateJpaVendorAdapter">
				<property name="database" value="${jdbc.database}" />
				<property name="showSql" value="${jdbc.show_sql}" />
			</bean>
		</property>
	</bean>

	<bean id="transactionManager" class="org.springframework.orm.jpa.JpaTransactionManager">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<tx:annotation-driven transaction-manager="transactionManager" />
	
	<bean id="dataSource" class="org.apache.tomcat.jdbc.pool.DataSource" destroy-method="close" >
		<property name="driverClassName" value="${jdbc.driverClassName}" />
		<property name="url" value="${jdbc.url}" />
		<property name="username" value="${jdbc.username}" />
		<property name="password" value="${jdbc.password}" />
		<property name="initialSize" value="${jdbc.initialSize}" />
		<property name="maxActive" value="${jdbc.maxActive}" />
		<property name="maxIdle" value="${jdbc.maxIdle}" />
		<property name="timeBetweenEvictionRunsMillis" value="${jdbc.timeBetweenEvictionRunsMillis}" />
		<property name="removeAbandoned" value="${jdbc.removeAbandoned}" />
		<property name="removeAbandonedTimeout" value="${jdbc.removeAbandonedTimeout}" />
		<property name="abandonWhenPercentageFull" value="${jdbc.abandonWhenPercentageFull}" />
		<property name="testOnBorrow" value="${jdbc.testOnBorrow}" />
		<property name="validationQuery" value="${jdbc.validationQuery}" />
		<property name="validationInterval" value="${jdbc.validationInterval}" />
		<property name="jmxEnabled" value="${jdbc.jmxEnabled}" />
	</bean>
	
	<!-- Utility Beans -->
	<bean id="sendMail" class="com.mintstreet.common.util.SendMail"/>
    <bean id="bureaulink" class="com.mintstreet.common.util.Bureaulink"/>
	<!-- DAO beans -->
	<bean id="masterQualificationDao" class="com.mintstreet.common.dao.MasterQualificationDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterCardIncomeDao" class="com.mintstreet.loan.card.dao.MasterCardIncomeDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="masterNatureBusinessDao" class="com.mintstreet.loan.card.dao.MasterNatureBusinessDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="masterCarDealerDao" class="com.mintstreet.common.dao.MasterCarDealerDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    
    <bean id="hlProductDao" class="com.mintstreet.loan.product.dao.HlProductDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
	<bean id="alProductDao" class="com.mintstreet.loan.product.dao.AlProductDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="elProductDao" class="com.mintstreet.loan.product.dao.ElProductDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="plProductDao" class="com.mintstreet.loan.product.dao.PlProductDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="aglProductDao" class="com.mintstreet.loan.agriloan.dao.MasterAgriProductDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
	 <bean id="masterBuilderDao" class="com.mintstreet.common.dao.MasterBuilderDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
     <bean id="masterEmployerDao" class="com.mintstreet.common.dao.MasterEmployerDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="stateDao" class="com.mintstreet.common.dao.MasterStateDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="cityDao" class="com.mintstreet.common.dao.MasterCityDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="loanPurposeDao" class="com.mintstreet.common.dao.LoanPurposeDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="loanCategoryDao" class="com.mintstreet.common.dao.LoanCategoryDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="loanTypeDao" class="com.mintstreet.common.dao.LoanTypeDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="employmentTypeDao" class="com.mintstreet.common.dao.EmploymentTypeDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="employeeOccupationTypeDao" class="com.mintstreet.common.dao.EmployeeOccupationTypeDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
     <bean id="masterCoApplicantDao" class="com.mintstreet.common.dao.MasterCoApplicantDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
     <bean id="countryDao" class="com.mintstreet.common.dao.CountryDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    <bean id="applicationFormHomeLoanDao" class="com.mintstreet.loan.homeloan.dao.ApplicationFormHomeLoanDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="applicationFormHomeLoanQuoteDao" class="com.mintstreet.loan.homeloan.dao.ApplicationFormHomeLoanQuoteDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="bankDao" class="com.mintstreet.common.dao.MasterBankDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="localityDao" class="com.mintstreet.common.dao.MasterLocalityDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterDistrictDao" class="com.mintstreet.common.dao.MasterDistrictDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterBranchDao" class="com.mintstreet.common.dao.MasterBranchDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="customerFeedbackDao" class="com.mintstreet.common.dao.CustomerFeedbackDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<!-- <bean id="validateFormConfigDao" class="com.mintstreet.common.dao.ValidateFormConfigDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	<!-- <bean id="validateFormListDao" class="com.mintstreet.common.dao.ValidateFormListDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	<!-- <bean id="validateRequestListDao" class="com.mintstreet.common.dao.ValidateRequestListDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	<bean id="validateRequestConfigDao" class="com.mintstreet.common.dao.ValidateRequestConfigDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<!-- <bean id="sourceLeadDao" class="com.mintstreet.common.dao.SourceLeadDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	<bean id="homeLoanHelper" class="com.mintstreet.loan.homeloan.util.HomeLoanHelper">
	</bean>
	<bean id="autoLoanHelper" class="com.mintstreet.loan.autoloan.util.AutoLoanHelper">
	</bean>
	<bean id="educationLoanHelper" class="com.mintstreet.loan.educationloan.util.EducationLoanHelper">
	</bean>
	<bean id="personalLoanHelper" class="com.mintstreet.loan.personal.util.PersonalLoanHelper">
	</bean>
	<bean id="templateDao" class="com.mintstreet.common.dao.TemplateDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterIndustryTypeDao" class="com.mintstreet.common.dao.MasterIndustryTypeDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="applicationFormHomeLoanCallsDao" class="com.mintstreet.loan.homeloan.dao.ApplicationFormHomeLoanCallsDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="applicationFormAutoLoanCallsDao" class="com.mintstreet.loan.autoloan.dao.ApplicationFormAutoLoanCallsDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="documentTypeDao" class="com.mintstreet.common.dao.DocumentTypeDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="carCompanyDao" class="com.mintstreet.loan.autoloan.dao.CarCompanyDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="carModelDao" class="com.mintstreet.loan.autoloan.dao.CarModelDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="carVariantDao" class="com.mintstreet.loan.autoloan.dao.CarVariantDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="applicationFormAutoLoanDao" class="com.mintstreet.loan.autoloan.dao.ApplicationFormAutoLoanDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="applicationFormAutoLoanQuoteDao" class="com.mintstreet.loan.autoloan.dao.ApplicationFormAutoLoanQuoteDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<!-- <bean id="bikeTypeDao" class="com.mintstreet.loan.autoloan.dao.BikeTypeDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="bikeCompanyDao" class="com.mintstreet.loan.autoloan.dao.BikeCompanyDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="bikeModelDao" class="com.mintstreet.loan.autoloan.dao.BikeModelDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="bikeVariantDao" class="com.mintstreet.loan.autoloan.dao.BikeVariantDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	<bean id="applicationFormLeadDao" class="com.mintstreet.common.dao.ApplicationFormLeadDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterInstituteDao" class="com.mintstreet.common.dao.MasterInstituteDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterGraduationDao" class="com.mintstreet.common.dao.MasterGraduationDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterCertificateDao" class="com.mintstreet.common.dao.MasterCertificateDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="residenceTypeDao" class="com.mintstreet.common.dao.ResidenceTypeDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="relationshipWithBankDao" class="com.mintstreet.common.dao.RelationshipWithBankDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="masterGenderDao" class="com.mintstreet.common.dao.MasterGenderDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterSalesTeamDao" class="com.mintstreet.common.dao.MasterSalesTeamDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterUniversityDao" class="com.mintstreet.common.dao.MasterUniversityDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterProfessionDao" class="com.mintstreet.common.dao.MasterProfessionDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterDealerDao" class="com.mintstreet.common.dao.MasterDealerDao" > 
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="bankLMSUserDao" class="com.mintstreet.common.dao.BankLMSUserDao" > 
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterCorpSalaryPackageDao" class="com.mintstreet.common.dao.MasterCorpSalaryPackageDao" > 
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<!-- <bean id="masterCorpSalaryPackageRankDao" class="com.mintstreet.common.dao.MasterCorpSalaryPackageRankDao" > 
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	<bean id="masterLabelTooltipDao" class="com.mintstreet.common.dao.MasterLabelTooltipDao" > 
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="applicationFormLeadCallsDao" class="com.mintstreet.common.dao.ApplicationFormLeadCallsDao" > 
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterLmsIntermediaryDao" class="com.mintstreet.common.dao.MasterLmsIntermediaryDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="intermediaryRelDao" class="com.mintstreet.common.dao.IntermediaryRelDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterProjectDao" class="com.mintstreet.loan.homeloan.dao.MasterProjectDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="bankLmsUserRoleDao" class="com.mintstreet.common.dao.BankLmsUserRoleDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterContentDao" class="com.mintstreet.common.dao.MasterContentDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
		
	<bean id="loanStatusDao" class="com.mintstreet.common.dao.LoanStatusDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="securityChecksDao" class="com.mintstreet.common.dao.SecurityChecksDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="biometricRequestDao" class="com.mintstreet.common.dao.BiometricRequestDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="biometricResponseDao" class="com.mintstreet.common.dao.BiometricResponseDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="sbiCampaignDao" class="com.mintstreet.common.dao.SbiCampaignDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="lastAppRefDao" class="com.mintstreet.common.dao.LastAppRefDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="bureauLinkRequestResponseDao" class="com.mintstreet.common.dao.BureauLinkRequestResponseDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="trackMainCampaignDao" class="com.mintstreet.campaign.dao.TrackMainCampaignDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="trackCampaignDao" class="com.mintstreet.campaign.dao.TrackCampaignDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="trackCampaignPlacementSourceDao" class="com.mintstreet.campaign.dao.TrackCampaignPlacementSourceDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="trackVisitDao" class="com.mintstreet.campaign.dao.TrackVisitDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="marTechDao" class="com.mintstreet.campaign.dao.MarTechDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<!-- <bean id="vlpRequestResponseDao" class="com.mintstreet.integration.vlp.education.dao.VlpRequestResponseDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	
	<bean id="apiPanLogDao" class="com.mintstreet.integration.pan.dao.PanLogDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="consentDao" class="com.mintstreet.common.dao.ConsentDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="cveProductDao" class="com.mintstreet.loan.cveloan.dao.MasterCveProductDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
	
	<bean id="ccmsConfigDao" class="com.mintstreet.consent.dao.CcmsConfigDao" >
	   	<property name="entityManagerFactory" ref="entityManagerFactory" />
    </bean>
    
	<bean id="commonService" class="com.mintstreet.common.service.CommonService">
		<property name="masterGenderDao" ref="masterGenderDao" />
		<property name="stateDao" ref="stateDao" />
		<property name="cityDao" ref="cityDao" />
		<property name="loanPurposeDao" ref="loanPurposeDao" />
		<property name="loanCategoryDao" ref="loanCategoryDao" />
		<property name="loanTypeDao" ref="loanTypeDao" />
		<property name="employmentTypeDao" ref="employmentTypeDao" />
		<property name="employeeOccupationTypeDao" ref="employeeOccupationTypeDao" />
		<property name="countryDao" ref="countryDao" />
		<property name="bankDao" ref="bankDao" />
		<!-- <property name="validateFormConfigDao" ref="validateFormConfigDao" /> -->
		<!-- <property name="validateFormListDao" ref="validateFormListDao" /> -->
		<!-- <property name="sourceLeadDao" ref="sourceLeadDao" /> -->
		<property name="masterDistrictDao" ref="masterDistrictDao" />
		<property name="masterBranchDao" ref="masterBranchDao" />
		<property name="masterBuilderDao" ref="masterBuilderDao" />
		<property name="masterEmployerDao" ref="masterEmployerDao" />
		<property name="localityDao" ref="localityDao" />
		<property name="documentTypeDao" ref="documentTypeDao" />
		<property name="templateDao" ref="templateDao" />
		<property name="applicationFormLeadDao" ref="applicationFormLeadDao"/>
		<property name="residenceTypeDao" ref="residenceTypeDao"/>
		<property name="relationshipWithBankDao" ref="relationshipWithBankDao"/>
		<property name="masterIndustryTypeDao" ref="masterIndustryTypeDao" />
		<property name="masterCoApplicantDao" ref="masterCoApplicantDao" />	
		<property name="masterCarDealerDao" ref="masterCarDealerDao" />
		<property name="hlProductDao" ref="hlProductDao" />
		<property name="alProductDao" ref="alProductDao" />
		<property name="elProductDao" ref="elProductDao" />
		<property name="plProductDao" ref="plProductDao" />
		<property name="aglProductDao" ref="aglProductDao" />
		<property name="masterSalesTeamDao" ref="masterSalesTeamDao" />
		<property name="masterProfessionDao" ref="masterProfessionDao" />
		<property name="masterDealerDao" ref="masterDealerDao" />
		<property name="bankLMSUserDao" ref="bankLMSUserDao" />
		<property name="masterCorpSalaryPackageDao" ref="masterCorpSalaryPackageDao" />
		<!-- <property name="masterCorpSalaryPackageRankDao" ref="masterCorpSalaryPackageRankDao" /> -->
		<property name="masterLabelTooltipDao" ref="masterLabelTooltipDao" />
		<property name="applicationFormLeadCallsDao" ref="applicationFormLeadCallsDao" />
		<property name="masterInstituteDao" ref="masterInstituteDao"/>
		<property name="intermediaryRelDao" ref="intermediaryRelDao"/>
		<property name="masterLmsIntermediaryDao" ref="masterLmsIntermediaryDao"/>
		<property name="bankLmsUserRoleDao" ref="bankLmsUserRoleDao"/>
		<property name="loanStatusDao" ref="loanStatusDao"/>
		<property name="masterContentDao" ref="masterContentDao"/>
		<property name="masterQualificationDao"  ref="masterQualificationDao"/>
		<property name="securityChecksDao"  ref="securityChecksDao"/>

		<property name="biometricRequestDao"  ref="biometricRequestDao"/>
		<property name="biometricResponseDao"  ref="biometricResponseDao"/>
		<property name="masterCBSResponseDao"  ref="masterCBSResponseDao"/>
		<property name="masterCBSCallDao"  ref="masterCBSCallDao"/>
		<property name="cbsProductMappingDao"  ref="cbsProductMappingDao"/>
		<property name="bureauLinkRequestResponseDao"  ref="bureauLinkRequestResponseDao"/>
		<!-- <property name="vlpRequestResponseDao"  ref="vlpRequestResponseDao"/>
		<property name="vlpExportDao"  ref="vlpExportDao"/>
		<property name="vlpLogInfoDao"  ref="vlpLogInfoDao"/> -->
		<property name="sbiCampaignDao"  ref="sbiCampaignDao"/>
		<!-- <property name="flipkartMicroDao"  ref="flipkartMicroDao"/>
		<property name="mingleDao"  ref="mingleDao"/> -->
		<property name="crmNextLogDao"  ref="crmNextLogDao"/>
		<property name="crmFetchLeadStatusDao"  ref="crmFetchLeadStatusDao"/>
		<property name="lastAppRefDao"  ref="lastAppRefDao"/>
		<property name="customerFeedbackDao"  ref="customerFeedbackDao"/>
		<property name="contactCenterLeadResponseDao"  ref="contactCenterLeadResponseDao"/>
		<property name="webServiceDao"  ref="webServiceDao"/>
		<property name="requestACallBackDao" ref="requestACallBackDao"/>
		<property name="trackMainCampaignDao" ref="trackMainCampaignDao" />
		<property name="trackCampaignDao" ref="trackCampaignDao" />
		<property name="trackCampaignPlacementSourceDao" ref="trackCampaignPlacementSourceDao" />
		<property name="trackVisitDao" ref="trackVisitDao" />
		<property name="applicationFormCveLoanDao" ref="applicationFormCveLoanDao"/>
	    <property name="applicationFormCaseCveDao" ref="applicationFormCaseCveDao"/>
	    <property name="consentDao"  ref="consentDao"/>
	    <property name="ccmsConfigDao"  ref="ccmsConfigDao"/>
	</bean>
	
	<bean id="campaignService" class="com.mintstreet.campaign.service.CampaignService">
		<property name="trackMainCampaignDao" ref="trackMainCampaignDao" />
		<property name="trackCampaignDao" ref="trackCampaignDao" />
		<property name="trackCampaignPlacementSourceDao" ref="trackCampaignPlacementSourceDao" />
		<property name="trackVisitDao" ref="trackVisitDao" />
		<property name="marTechDao" ref="marTechDao" />
	</bean>
	
	<bean id="validatorService" class="com.mintstreet.common.service.ValidatorService">
		<!-- <property name="validateRequestListDao" ref="validateRequestListDao" /> -->
		<property name="validateRequestConfigDao" ref="validateRequestConfigDao" />
		<property name="masterQualificationDao"  ref="masterQualificationDao"/>
	</bean>
	
	<bean id="processManagerImpl" class="com.mintstreet.common.bo.impl.ProcessManagerImpl"></bean>
	<bean id="processManagerHomeImpl" class="com.mintstreet.loan.homeloan.bo.impl.HomeProcessManagerImpl"></bean>
	<bean id="processManagerAutoImpl" class="com.mintstreet.loan.autoloan.bo.impl.AutoProcessManagerImpl"></bean>
	<bean id="processManagerEducationImpl" class="com.mintstreet.loan.educationloan.bo.impl.EducationProcessManagerImpl"></bean>
	<bean id="processManagerPersonalImpl" class="com.mintstreet.loan.personal.bo.impl.PersonalProcessManagerImpl"></bean>
	<bean id="communicationManagerImpl" class="com.mintstreet.common.bo.impl.CommunicationManagerImpl"></bean>
	<!-- <bean id="campaignManager" class="com.mintstreet.campaign.impl.CampaignManager"></bean> -->
	
	<bean id="homeLoanAction" class="com.mintstreet.loan.homeloan.action.HomeLoanAction" scope="prototype"></bean>
	<bean id="homeTopupLoanAction" class="com.mintstreet.loan.homeloan.action.HomeTopupLoanAction" scope="prototype"></bean>
	<bean id="autoLoanAction" class="com.mintstreet.loan.autoloan.action.AutoLoanAction" scope="prototype"></bean>
	<bean id="educationLoanAction" class="com.mintstreet.loan.educationloan.action.EducationLoanAction" scope="prototype"></bean>
	<bean id="personalLoanAction" class="com.mintstreet.loan.personal.action.PersonalLoanAction" scope="prototype"></bean>
	<bean id="fileUploadAction" class="com.mintstreet.common.action.FileUploadAction" scope="prototype"></bean> 
	<bean id="applicationStatusAction" class="com.mintstreet.common.action.ApplicationStatusAction" scope="prototype"></bean>
	<bean id="commonLoanAction" class="com.mintstreet.common.action.CommonLoanAction" scope="prototype"></bean>
	<!-- <bean id="customerFeedbackAction" class="com.mintstreet.common.action.CustomerFeedbackAction" scope="prototype"></bean> -->
	<!-- <bean id="vidyaLakshmiLoanAction" class="com.mintstreet.integration.vlp.education.action.VidyaLakshmiLoanAction" scope="prototype"></bean> -->
	<bean id="cronScheduleAction" class="com.mintstreet.common.action.CronScheduleAction" scope="prototype"></bean>
	
	<bean id="campaignAction" class="com.mintstreet.common.action.CampaignAction" scope="prototype"></bean>
	<!-- <bean id="flipkartAction" class="com.mintstreet.common.action.FlipkartMicroAction" scope="prototype"></bean>
	<bean id="mingleLead" class="com.mintstreet.mingleLead.action.MingleLeadAction" scope="prototype"></bean> -->
	<bean id="uploadLead" class="com.mintstreet.uploadLead.action.UploadLead" scope="prototype"></bean>
	<bean id="privacyNoticeAction" class="com.mintstreet.consent.action.PrivacyNoticeAction" scope="prototype"></bean>
	<bean id="infronicsLead" class="com.mintstreet.uploadLead.action.InfronicsLead" scope="prototype"></bean>
	<bean id="campaignCallbackAction" class="com.mintstreet.loan.campaign.action.CampaignCallbackAction" scope="prototype"></bean>
    <bean id="cveLoanAction" class="com.mintstreet.loan.cveloan.action.CveLoanAction" scope="prototype"></bean>
	<bean id="cveProcessManagerPersonalImpl" class="com.mintstreet.loan.cveloan.bo.impl.CveProcessManagerImpl"></bean>

	<!--  Ui Beans  starts-->
	<bean id="homeLoanService" class="com.mintstreet.loan.homeloan.service.HomeLoanService">
		<property name="applicationFormHomeLoanQuoteDao" ref="applicationFormHomeLoanQuoteDao"/>
		<property name="applicationFormHomeLoanDao" ref="applicationFormHomeLoanDao"/>
		<property name="applicationFormHomeLoanCallsDao" ref="applicationFormHomeLoanCallsDao" />
		<property name="masterProjectDao" ref="masterProjectDao" />
		<property name="hlProductDao" ref="hlProductDao" />
		<property name="masterCBSResponseDao"  ref="masterCBSResponseDao"/>
		<property name="loanPurposeDao" ref="loanPurposeDao" />
		<property name="masterCBSCallDao"  ref="masterCBSCallDao"/>
	</bean>
	
	<bean id="autoLoanService" class="com.mintstreet.loan.autoloan.service.AutoLoanService">
		<!-- <property name="bikeTypeDao" ref="bikeTypeDao" />
		<property name="bikeCompanyDao" ref="bikeCompanyDao" />
		<property name="bikeModelDao" ref="bikeModelDao" />
		<property name="bikeVariantDao" ref="bikeVariantDao" /> -->
		<property name="carCompanyDao" ref="carCompanyDao" />
		<property name="carModelDao" ref="carModelDao" />
		<property name="carVariantDao" ref="carVariantDao" />
		<property name="applicationFormAutoLoanQuoteDao" ref="applicationFormAutoLoanQuoteDao"/>
		<property name="applicationFormAutoLoanDao" ref="applicationFormAutoLoanDao"/>
		<property name="applicationFormAutoLoanCallsDao" ref="applicationFormAutoLoanCallsDao" />
		<property name="alProductDao" ref="alProductDao" />
		<property name="masterCBSResponseDao"  ref="masterCBSResponseDao"/>
		<property name="loanPurposeDao" ref="loanPurposeDao" />
		<property name="masterCBSCallDao"  ref="masterCBSCallDao"/>
	</bean>
	<bean id="applicationFormEducationLoanQuoteDao" class="com.mintstreet.loan.educationloan.dao.ApplicationFormEducationLoanQuoteDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="applicationFormEducationLoanDao" class="com.mintstreet.loan.educationloan.dao.ApplicationFormEducationLoanDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
		<bean id="applicationFormEducationLoanCallsDao" class="com.mintstreet.loan.educationloan.dao.ApplicationFormEducationLoanCallsDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
		<bean id="masterCourseTypeDao" class="com.mintstreet.loan.educationloan.dao.MasterCourseTypeDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="educationLoanService" class="com.mintstreet.loan.educationloan.service.EducationLoanService">
		<property name="applicationFormEducationLoanQuoteDao" ref="applicationFormEducationLoanQuoteDao"/>
		<property name="applicationFormEducationLoanDao" ref="applicationFormEducationLoanDao"/>
		<property name="applicationFormEducationLoanCallsDao" ref="applicationFormEducationLoanCallsDao" />
		
		<property name="masterInstituteDao" ref="masterInstituteDao"/>
		<property name="masterCertificateDao" ref="masterCertificateDao"/>
		<property name="masterGraduationDao" ref="masterGraduationDao"/>
		<property name="masterUniversityDao" ref="masterUniversityDao"/>
		<property name="masterCourseTypeDao" ref="masterCourseTypeDao"/>
		<property name="elProductDao" ref="elProductDao" />
		<property name="masterCBSResponseDao"  ref="masterCBSResponseDao"/>
		<property name="loanPurposeDao" ref="loanPurposeDao" />
		<property name="masterCBSCallDao"  ref="masterCBSCallDao"/>
	</bean>
	
	<bean id="applicationFormPersonalLoanQuoteDao" class="com.mintstreet.loan.personal.dao.ApplicationFormPersonalLoanQuoteDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="applicationFormPersonalLoanDao" class="com.mintstreet.loan.personal.dao.ApplicationFormPersonalLoanDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="applicationFormPersonalLoanCallsDao" class="com.mintstreet.loan.personal.dao.ApplicationFormPersonalLoanCallsDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
        
	
	<bean id="personalLoanService" class="com.mintstreet.loan.personal.service.PersonalLoanService">
		<property name="applicationFormPersonalLoanQuoteDao" ref="applicationFormPersonalLoanQuoteDao"/>
		<property name="applicationFormPersonalLoanDao" ref="applicationFormPersonalLoanDao"/>
		<property name="applicationFormPersonalLoanCallsDao" ref="applicationFormPersonalLoanCallsDao" />
		<property name="masterInstituteDao" ref="masterInstituteDao"/>
		<property name="plProductDao" ref="plProductDao" />
		<property name="masterCBSResponseDao"  ref="masterCBSResponseDao"/>
		<property name="loanPurposeDao" ref="loanPurposeDao" />
		<property name="masterCBSCallDao"  ref="masterCBSCallDao"/>
		<property name="applicationFormCveLoanDao"  ref="applicationFormCveLoanDao"/>
	</bean>
	

	<bean id="integrationService" class="com.mintstreet.integration.common.service.IntegrationService">
		<property name="applicationFormHomeLoanDao" ref="applicationFormHomeLoanDao" />
		<property name="applicationFormAutoLoanDao" ref="applicationFormAutoLoanDao" />
		<property name="applicationFormEducationLoanDao" ref="applicationFormEducationLoanDao" />
		<property name="applicationFormPersonalLoanDao" ref="applicationFormPersonalLoanDao" />
		<property name="applicationFormCreditCardDao" ref="applicationFormCreditCardDao" />
		<property name="applicationFormAgriLoanDao" ref="applicationFormAgriLoanDao" />
		<property name="apiPanLogDao" ref="apiPanLogDao" />
	</bean>
	
	<bean id="cveLoanService" class="com.mintstreet.loan.cveloan.service.CveLoanService">
		<property name="cveProductDao"  ref="cveProductDao"/>
	</bean>
	
	<bean id="consentService" class="com.mintstreet.consent.service.ConsentService">
	</bean>

	<!-- Action beans -->
	<bean id="taskExecutor" class="org.springframework.scheduling.concurrent.ThreadPoolTaskExecutor">
	  <property name="corePoolSize" value="200" />
	  <property name="maxPoolSize" value="500" />
	  <property name="keepAliveSeconds" value="45" />
	  <property name="allowCoreThreadTimeOut" value="true" />
	  <property name="queueCapacity" value="5000" />
	</bean>
	<!-- Service beans -->
	<bean id="taskExecutorService" class="com.mintstreet.common.service.TaskExecutorService">
	  	<!-- <constructor-arg ref="taskExecutor" /> -->
	</bean>
	<bean id="generatePDF" class="com.mintstreet.common.util.GeneratePDF"></bean>
	<bean id="SbiUtil" class="com.mintstreet.common.util.SbiUtil"></bean>
	<bean id="validatorManager" class="com.mintstreet.common.validation.ValidatorManager"></bean>
	<bean id="stateManager" class="com.mintstreet.common.state.StateManager"></bean>
	<bean id="commonEngine" class="com.mintstreet.common.engine.CommonEngine"></bean>
	<bean id="bureauLinkUtil" class="com.mintstreet.common.util.BureauLinkUtil" />
	<bean id="demographicUtil" class="com.mintstreet.common.util.DemographicUtil"></bean>
	<bean id="ekycBiometricUtil" class="com.mintstreet.common.util.EKYCBiometricUtil"></bean>
	<!-- <bean id="crmService" class="com.mintstreet.common.util.CRMService"></bean> -->
	<bean id="crmServiceNew" class="com.mintstreet.common.util.CRMServiceNew"></bean>
	<bean id="panServiceAction" class="com.mintstreet.integration.pan.action.PanServiceAction"></bean>
	
	<bean id="masterCBSResponseDao" class="com.mintstreet.common.dao.MasterCBSResponseDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="masterCBSCallDao" class="com.mintstreet.common.dao.MasterCBSCallDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>

	<bean id="applicationFormCveLoanDao" class="com.mintstreet.loan.cveloan.dao.ApplicationFormCveLoanDao" >
                <property name="entityManagerFactory" ref="entityManagerFactory" />
        </bean>

	<bean id="applicationFormCaseCveDao" class="com.mintstreet.loan.cveloan.dao.ApplicationFormCaseCveDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>

	<bean id="cbsUtil" class="com.mintstreet.common.util.CbsUtil"></bean>
	
	<bean id="cbsProductMappingDao" class="com.mintstreet.common.dao.CbsProductMappingDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<!-- <bean id="vlpExportDao" class="com.mintstreet.integration.vlp.education.dao.VLPExportDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="vlpDupCheck" class="com.mintstreet.integration.vlp.education.dao.VlpDupCheckDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>

	<bean id="vlpLogInfoDao" class="com.mintstreet.integration.vlp.education.dao.VLPLogInfoDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	<!-- <bean id="flipkartMicroDao" class="com.mintstreet.common.dao.FlipkartMicroLeadDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="mingleDao" class="com.mintstreet.mingleLead.dao.MingleDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean> -->
	<bean id="crmNextLogDao" class="com.mintstreet.common.dao.CRMNextLogDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="crmFetchLeadStatusDao" class="com.mintstreet.common.dao.CRMFetchLeadStatusDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	<bean id="contactCenterLeadResponseDao" class="com.mintstreet.common.dao.ContactCenterLeadResponseDao">
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<bean id="requestACallBackDao" class="com.mintstreet.common.dao.RequestACallBackDao" >
		<property name="entityManagerFactory" ref="entityManagerFactory" />
	</bean>
	
	<!-- <bean id="vlpGetFileListScheduler" class="com.mintstreet.integration.vlp.education.action.VlpGetFileListScheduler" ></bean>
	<bean id="vlpGetFile" class="com.mintstreet.integration.vlp.education.action.VlpGetFile" ></bean>
	<bean id="vlpStatusUpload" class="com.mintstreet.integration.vlp.education.action.VlpStatusUpload" ></bean>
	<bean id="vlpProcessFile" class="com.mintstreet.integration.vlp.education.action.VLPProcessFile"></bean>
	<bean id="vlpStatusReport" class="com.mintstreet.integration.vlp.education.action.VlpStatusReport"></bean>
	<bean id="uploadFileStatus" class="com.mintstreet.integration.vlp.education.service.UploadFileStatus"></bean>
	<bean id="vlpFileExportInfo" class="com.mintstreet.integration.vlp.education.entity.VLPFileExportInfo"></bean>
	<bean id="vlpLogInfo" class="com.mintstreet.integration.vlp.education.entity.VLPLogInfo"></bean>
	<bean id="vlpGetFileListTest" class="com.mintstreet.integration.vlp.education.action.VlpGetFileListTest" ></bean> -->
	
	<bean id="commonLoanWebServiceAction" class="com.mintstreet.webservice.action.CommonLoanWebServiceAction" scope="prototype"></bean>
	<bean id="ocasWebServiceUtil" class="com.mintstreet.common.util.OCASWebServiceUtil"></bean>
	
	<bean id="callBack" class="com.mintstreet.callback.service.CallBackService"></bean>	
	<bean id="uploadBean" class="com.mintstreet.uploadLead.entity.UploadBean"></bean>
	
	<!-- <bean id="mingleBean" class="com.mintstreet.mingleLead.entity.MingleBean"></bean> -->
	<bean id="crmNextLogBean" class="com.mintstreet.common.entity.CRMNextLog"></bean>
	<bean id="crmFetchLeadStatusBean" class="com.mintstreet.common.entity.CRMFetchLeadStatus"></bean>
	<bean id="crmFetchLeadStatusApi" class="com.mintstreet.common.util.CRMFetchLeadStatusApi"></bean>
	<bean id="requestHandler" class="com.mintstreet.common.util.RequestHandler"></bean>
	
	<bean id="RefGenerateUtil" class="com.mintstreet.common.util.RefGenerateUtil"></bean>
	<bean id="refGenerateUtilHL" class="com.mintstreet.common.util.RefGenerateUtilHL"></bean>
	<bean id="refGenerateUtilAL" class="com.mintstreet.common.util.RefGenerateUtilAL"></bean>
	<bean id="refGenerateUtilPL" class="com.mintstreet.common.util.RefGenerateUtilPL"></bean>
	<bean id="refGenerateUtilEL" class="com.mintstreet.common.util.RefGenerateUtilEL"></bean>
	<bean id="refGenerateUtilAGL" class="com.mintstreet.common.util.RefGenerateUtilAGL"></bean>
	<bean id="refGenerateUtilCC" class="com.mintstreet.common.util.RefGenerateUtilCC"></bean>
	<bean id="requestACallBack" class="com.mintstreet.common.entity.RequestACallBack"></bean>
	<!-- <bean id="unzipUtility" class="com.mintstreet.integration.vlp.education.util.UnzipUtility"></bean> -->
	
	<bean id="consentUtil" class="com.mintstreet.common.util.ConsentUtil"></bean>
	<bean id="ccmsConfig" class="com.mintstreet.consent.entity.CCMSConfig"></bean>
	
	<import resource="webServiceContext.xml"></import>
	<import resource="agriLoanContext.xml"></import>
	<import resource="creditCardContext.xml"></import>
	<!-- <import resource="instantloanContext.xml"></import> -->


</beans>


------------


package com.mintstreet.uploadLead.action;

import java.io.ByteArrayInputStream;
import java.io.UnsupportedEncodingException;
import java.security.InvalidAlgorithmParameterException;
import java.security.InvalidKeyException;
import java.security.NoSuchAlgorithmException;
import java.security.SecureRandom;
import java.security.spec.InvalidKeySpecException;
import java.security.spec.KeySpec;
import java.util.Base64;
import java.util.Date;

import javax.crypto.BadPaddingException;
import javax.crypto.Cipher;
import javax.crypto.IllegalBlockSizeException;
import javax.crypto.NoSuchPaddingException;
import javax.crypto.SecretKey;
import javax.crypto.SecretKeyFactory;
import javax.crypto.spec.GCMParameterSpec;
import javax.crypto.spec.PBEKeySpec;
import javax.crypto.spec.SecretKeySpec;

import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;
import org.apache.struts2.result.StreamResult;
import org.json.JSONException;
import org.json.JSONObject;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.HttpRequestMethodNotSupportedException;

import com.mintstreet.callback.service.CallBackService;
import com.mintstreet.common.action.CommonLoanAction;
import com.mintstreet.common.entity.ApplicationFormLead;
import com.mintstreet.common.service.CommonService;
import com.mintstreet.common.service.TaskExecutorService;
import com.mintstreet.common.util.Constants;
import com.mintstreet.common.util.EncryptDecryptUtil;
import com.mintstreet.common.util.RequestUtil;
import com.mintstreet.common.validation.ValidatorUtil;
import com.mintstreet.uploadLead.entity.UploadBean;

public class UploadLead extends CommonLoanAction {
  private static final long serialVersionUID = 1L;
  
  private static final int KEY_LENGTH = 256;
  private static final int ITERATION_COUNT = 65536;
  private static final int DEFAULT_GCM_IV_NONCE_SIZE_BYTES = 12;
  private static final int DEFAULT_GCM_AUTHENTICATION_TAG_SIZE_BITS = 128;
  private static final String CIPHER_ALGORITHM = "AES/GCM/NoPadding";
  private String secreteKey = Constants.UPLOADLEAD_SECRETKEY;
  
  private static final Logger logger = LogManager.getLogger(UploadLead.class.getName());
  
  @Autowired
  private CommonService commonService;
  
  @Autowired
  private TaskExecutorService taskExecutorService;
  
  @Autowired
  private CallBackService callBackService;
  
  public StreamResult quickUploadLead() throws JSONException, HttpRequestMethodNotSupportedException, InvalidKeyException, NoSuchPaddingException, NoSuchAlgorithmException, InvalidAlgorithmParameterException, BadPaddingException, IllegalBlockSizeException, InvalidKeySpecException, UnsupportedEncodingException {
    StringBuilder str = new StringBuilder();
    str = str.append("{ \"response\" :[");
    if(RequestUtil.getServletRequest().getMethod().equalsIgnoreCase("POST")) {
    try {
    	for (int i = 0; i < this.quickLead.size(); i++) {
    		UploadBean info = this.quickLead.get(i);
    		if(preValidation(info)) {
    			info.setAuth_Key(decryptData(info.getAuth_Key(), EncryptDecryptUtil.decrypt(secreteKey)));
        		info.setCampaign_Name(decryptData(info.getCampaign_Name(), EncryptDecryptUtil.decrypt(secreteKey)));
        		info.setMobile_Number(decryptData(info.getMobile_Number(), EncryptDecryptUtil.decrypt(secreteKey)));
        		info.setReference_Number(decryptData(info.getReference_Number(), EncryptDecryptUtil.decrypt(secreteKey)));
        		info.setSMS_Content(decryptData(info.getSMS_Content(), EncryptDecryptUtil.decrypt(secreteKey)));
        		
        		this.quickLead.set(i, info);
    		} else {
    			JSONObject jsonObj = new JSONObject();
        		jsonObj.put("reference number", "");
                jsonObj.put("status", "FAILED");
                jsonObj.put("error", "system error");
                str.append(jsonObj.toString());
        		str.append("]}");
        		String res = encryptData(str.toString(), EncryptDecryptUtil.decrypt(secreteKey));
        		logger.info("UploadLead. java :: LNO: 87 encrypted responses is : " + res);
        	    return new StreamResult(new ByteArrayInputStream(res.toString().getBytes()));
    		}
    	}
    	
    	if(!validateRequest()) {
    		String m = getMessage();
    		JSONObject jsonObj = new JSONObject();
    		jsonObj.put("reference number", "");
            jsonObj.put("status", "FAILED");
            jsonObj.put("error", m);
            str.append(jsonObj.toString());
    		str.append("]}");
    		String res = encryptData(str.toString(), EncryptDecryptUtil.decrypt(secreteKey));
    		logger.info("UploadLead. java :: LNO: 101 encrypted responses is : " + res);
    	    return new StreamResult(new ByteArrayInputStream(res.toString().getBytes()));
    	}
    	    
    if (((UploadBean)this.quickLead.get(0)).getSMS_Content().contains("MISSED_CALL")) {
        if (this.quickLead != null) {
          for (int i = 0; i < this.quickLead.size(); i++) {
            boolean isMobileInDedupe = false;
            boolean isUniqueRefNo = false;
            boolean isValidCampaignName = false;
            ApplicationFormLead formLead = new ApplicationFormLead();
            JSONObject jsonObj = new JSONObject();
            int productId = 0;
            if (((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("MISSED_CALL")) {
            	
            	String product = ((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) ? 
             		   " for " + ((UploadBean)this.quickLead.get(i)).getCampaign_Name() + " loan": ""; 
             	String logMessage = "Campaign Lead :: Missed Call lead " + product;
             	logger.info(logMessage);

              if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("HOME")) {
                productId = 1;
              } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && 
                !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("CAR") || (
            	  (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AUTO"))) {
            	  productId = 2;
                
              } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && 
                !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("PERSONAL") || (
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("GOLD"))) {
                productId = 3;
              }
              else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (
                      (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AGRI")) {
                  productId = 15;
              }
              else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && 
                !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("SME")) {
                productId = 20;
              } else {
                productId = 0;
              } 
              
	              if (EncryptDecryptUtil.decrypt(Constants.AUTH_KEY).equalsIgnoreCase(((UploadBean)this.quickLead.get(i)).getAuth_Key())) {
	                if (ValidatorUtil.isValidMobile(((UploadBean)this.quickLead.get(i)).getMobile_Number())) {
	                  if (ValidatorUtil.isValid(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (productId == 1 || productId == 2 || productId == 3 || productId == 20 || productId == 15)) {
	                    isMobileInDedupe = this.commonService
	                      .isMobileFoundForDedupeInLead(((UploadBean)this.quickLead.get(i)).getMobile_Number(), productId);
	                    isValidCampaignName = true;
	                  } else {
	                    jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
	                    jsonObj.put("error", "invalid campaign name.");
	                    jsonObj.put("status", "FAILED");
	                    str.append(jsonObj.toString());
	                    i++;
	                  } 
	                  if (ValidatorUtil.isValid(((UploadBean)this.quickLead.get(i)).getReference_Number())) {
	                    isUniqueRefNo = this.commonService
	                      .isUniqueReferenceNo(((UploadBean)this.quickLead.get(i)).getReference_Number(), productId);
	                  } 
	                  if (isMobileInDedupe && isUniqueRefNo && isValidCampaignName) {
	                    formLead.setLeadMobileNo(((UploadBean)this.quickLead.get(i)).getMobile_Number());
	                    if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("HOME")) {
	                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
	                      formLead.setLeadLoanPurposeId(Integer.valueOf(1));
	                    } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("CAR") || ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AUTO"))) {
	                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
	                      formLead.setLeadLoanPurposeId(Integer.valueOf(3));
	                    } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("PERSONAL") || ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("GOLD"))) {
	                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
	                      //formLead.setLeadLoanPurposeId(Integer.valueOf(13));
						  formLead.setLeadLoanPurposeId(Integer.valueOf(4));
	                    } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("SME")) {
	                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
	                      formLead.setLeadLoanPurposeId(Integer.valueOf(16));
	                    } 
	                    else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AGRI")) {
	                        formLead.setLeadProductTypeId(Integer.valueOf(productId));
	                        formLead.setLeadLoanPurposeId(Integer.valueOf(15));
	                      }else {
	                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
	                    } 
	                    formLead.setLeadCampaignSourceId(((UploadBean)this.quickLead.get(i)).getReference_Number());
	                    formLead.setLeadDataSourceId(Constants.LEAD_DATA_SOURCE_ID_UPLOAD);
	                    formLead.setLeadLoanStatusId(Integer.valueOf(Constants.CALL_LOGS_MESSAGE_STATE105_ID));
	                    formLead.setLeadCampaignId(Integer.valueOf(302));
	                    formLead.setLeadActive("Y");
	                    formLead.setLeadDeleted("N");
	                    formLead.setLeadMobileVerificationCodeVerified("N");
	                    formLead.setLeadReceiveDatetime(new Date());
	                    formLead.setLeadEntryTime(new Date());
	                    formLead.setLeadEntryDate(new Date());
	                    formLead.setLeadLastUpdated(new Date());
	                    //formLead.setLeadAppVLPStudentAppId(Integer.valueOf(0));
	                    formLead.setLeadMobileAlertCount(Integer.valueOf(1));
	                    formLead.setLeadBankId(Constants.LEAD_BANK_ID);
	                    formLead.setLeadAppContactCenterLocation(1);
	                    formLead.setLeadFulfillmentGroupId(Integer.valueOf(6));
	                   	formLead = this.commonService.save(formLead);
	                    if (formLead == null) {
	                      jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
	                      jsonObj.put("error", "system error");
	                      jsonObj.put("status", "FAILED");
	                      str.append(jsonObj.toString());
	                    } else {
	                      jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
	                      jsonObj.put("status", "SUCCESS");
	                      jsonObj.put("error", "");
	                      str.append(jsonObj.toString());
	                      if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((
	                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("HOME") || (
	                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("CAR") || (
	                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AUTO") || (
	                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("PERSONAL") || (
	                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("GOLD") || (
	                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("SME")  || (
	                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AGRI")))
	                      {
	                        this.taskExecutorService.SendingSMSForInfronics(Integer.valueOf(0), Integer.valueOf(1), formLead, null);
	                        	this.callBackService.getcallBackService(formLead); 
	                        }
	                     }
	                 } else if (!isMobileInDedupe) {
	                    jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
	                    jsonObj.put("status", "FAILED");
	                    jsonObj.put("error", "duplicate mobile number.");
	                    str.append(jsonObj.toString());
	                  } else {
	                    jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
	                    jsonObj.put("status", "FAILED");
	                    jsonObj.put("error", "duplicate reference number.");
	                    str.append(jsonObj.toString());
	                  } 
	                } else {
	                  jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
	                  jsonObj.put("status", "FAILED");
	                  jsonObj.put("error", "invalid mobile number.");
	                  str.append(jsonObj.toString());
	                } 
	              } else {
	                jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
	                jsonObj.put("status", "FAILED");
	                jsonObj.put("error", "invalid auth key.");
	                str.append(jsonObj.toString());
	              } 
            } else {
              jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
              jsonObj.put("status", "FAILED");
              jsonObj.put("error", "invalid SMS Content.");
              str.append(jsonObj.toString());
            } 
          } 
        } else {
          logger.warn("The quicklead coming is null");
        } 
      } else {
        if (this.quickLead != null) {
          for (int i = 0; i < this.quickLead.size(); i++) {
            boolean isMobileInDedupe = false;
            boolean isUniqueRefNo = false;
            boolean isValidCampaignName = false;
            ApplicationFormLead formLead = new ApplicationFormLead();
            JSONObject jsonObj = new JSONObject();
            int productId = 0;
            if (((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("HOME") || ((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("CAR") || ((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("PERSONAL") || ((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("GOLD") || ((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("LAP") || ((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("SME") || ((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("AUTO") || ((UploadBean)this.quickLead.get(i)).getSMS_Content().equals("AGRI")) {
            	
            	String product = ((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) ? 
              		   " for " + ((UploadBean)this.quickLead.get(i)).getCampaign_Name() + " loan": ""; 
              	String logMessage = "Campaign Lead :: SMS lead " + product;
              	logger.info(logMessage);

              if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("HOME")) {
                productId = 1;
              } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && 
                !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("CAR") || (
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AUTO"))) {
                productId = 2;
              } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && 
                !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("PERSONAL") || (
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("GOLD") || (
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("LAP"))) {
                productId = 3;
              } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && 
                !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (
                (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("SME")) {
                productId = 20;
              }
              else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (
                      (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AGRI")) {
                      productId = 15;
               } else {
                productId = 0;
              } 
            	
              if (EncryptDecryptUtil.decrypt(Constants.AUTH_KEY).equalsIgnoreCase(((UploadBean)this.quickLead.get(i)).getAuth_Key())) {
                if (ValidatorUtil.isValidMobile(((UploadBean)this.quickLead.get(i)).getMobile_Number())) {
                  if (ValidatorUtil.isValid(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (productId == 1 || productId == 2 || productId == 3 || productId == 20 || productId == 15)) {
                    isMobileInDedupe = this.commonService
                      .isMobileFoundForDedupeInLead(((UploadBean)this.quickLead.get(i)).getMobile_Number(), productId);
                    isValidCampaignName = true;
                  } else {
                    jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
                    jsonObj.put("error", "invalid campaign name.");
                    jsonObj.put("status", "FAILED");
                    str.append(jsonObj.toString());
                    i++;
                  } 
                  if (ValidatorUtil.isValid(((UploadBean)this.quickLead.get(i)).getReference_Number())) {
                    isUniqueRefNo = this.commonService
                      .isUniqueReferenceNo(((UploadBean)this.quickLead.get(i)).getReference_Number(), productId);
                  } 
                  if (isMobileInDedupe && isUniqueRefNo && isValidCampaignName) {
                    formLead.setLeadMobileNo(((UploadBean)this.quickLead.get(i)).getMobile_Number());
                    if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("HOME")) {
                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
                      formLead.setLeadLoanPurposeId(Integer.valueOf(1));
                    } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("CAR") || ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AUTO"))) {
                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
                      formLead.setLeadLoanPurposeId(Integer.valueOf(3));
                    } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && (((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("PERSONAL") || ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("GOLD") || ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("LAP"))) {
                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
                      //formLead.setLeadLoanPurposeId(Integer.valueOf(13));			
                      formLead.setLeadLoanPurposeId(Integer.valueOf(4));
                    } else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("SME")) {
                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
                      formLead.setLeadLoanPurposeId(Integer.valueOf(16));
                    }
                    else if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AGRI")) {
                        formLead.setLeadProductTypeId(Integer.valueOf(productId));
                        formLead.setLeadLoanPurposeId(Integer.valueOf(15));
                    } else {
                      formLead.setLeadProductTypeId(Integer.valueOf(productId));
                    } 
                    formLead.setLeadCampaignSourceId(((UploadBean)this.quickLead.get(i)).getReference_Number());
                    formLead.setLeadDataSourceId(Constants.LEAD_DATA_SOURCE_ID_UPLOAD);
                    formLead.setLeadLoanStatusId(Integer.valueOf(Constants.CALL_LOGS_MESSAGE_STATE105_ID));
                    formLead.setLeadCampaignId(Integer.valueOf(3));
                    formLead.setLeadActive("Y");
                    formLead.setLeadDeleted("N");
                    formLead.setLeadMobileVerificationCodeVerified("N");
                    formLead.setLeadReceiveDatetime(new Date());
                    formLead.setLeadEntryTime(new Date());
                    formLead.setLeadEntryDate(new Date());
                    formLead.setLeadLastUpdated(new Date());
                    //formLead.setLeadAppVLPStudentAppId(Integer.valueOf(0));
                    formLead.setLeadMobileAlertCount(Integer.valueOf(1));
                    formLead.setLeadBankId(Constants.LEAD_BANK_ID);
                    formLead.setLeadAppContactCenterLocation(1);
                    formLead.setLeadFulfillmentGroupId(Integer.valueOf(6));
                    formLead = this.commonService.save(formLead);
                    if (formLead == null) {
                      jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
                      jsonObj.put("error", "system error");
                      jsonObj.put("status", "FAILED");
                      str.append(jsonObj.toString());
                    } else {
                      jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
                      jsonObj.put("status", "SUCCESS");
                      jsonObj.put("error", "");
                      str.append(jsonObj.toString());
                      if (((UploadBean)this.quickLead.get(i)).getCampaign_Name() != null && !"".equals(((UploadBean)this.quickLead.get(i)).getCampaign_Name()) && ((
                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("HOME") || (
                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("CAR") || (
                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AUTO") || (
                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("PERSONAL") || (
                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("GOLD") || (
                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("LAP") || (
                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("SME") || (
                        (UploadBean)this.quickLead.get(i)).getCampaign_Name().equals("AGRI")))
                      {
                        this.taskExecutorService.SendingSMSForInfronics(Integer.valueOf(0), Integer.valueOf(1), formLead, null);
                        this.callBackService.getcallBackService(formLead);
                      }
                      }
                  } else if (!isMobileInDedupe) {
                    jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
                    jsonObj.put("status", "FAILED");
                    jsonObj.put("error", "duplicate mobile number.");
                    str.append(jsonObj.toString());
                  } else {
                    jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
                    jsonObj.put("status", "FAILED");
                    jsonObj.put("error", "duplicate reference number.");
                    str.append(jsonObj.toString());
                  } 
                } else {
                  jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
                  jsonObj.put("status", "FAILED");
                  jsonObj.put("error", "invalid mobile number.");
                  str.append(jsonObj.toString());
                } 
              } else {
                jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
                jsonObj.put("status", "FAILED");
                jsonObj.put("error", "invalid auth key.");
                str.append(jsonObj.toString());
              } 
            } else {
              jsonObj.put("reference number", ((UploadBean)this.quickLead.get(i)).getReference_Number());
              jsonObj.put("status", "FAILED");
              jsonObj.put("error", "invalid SMS Content.");
              str.append(jsonObj.toString());
            } 
          } 
        } else {
          logger.warn("The quicklead coming is null");
        } 
      } 
	    } catch (JSONException e) {
	        this.json.put("error", "1");
	        logger.info("UploadLead. java :: LNO: 417 : Exception Caught " + e);
	     } catch (Exception e) {
	      this.json.put("error", "1");
	      logger.info("UploadLead. java :: LNO: 420 : Exception Caught " + e);
	    } 
    } else {
    	logger.info("UploadLead. java :: Got HTTP request of type " + RequestUtil.getServletRequest().getMethod());
    	throw new HttpRequestMethodNotSupportedException("POST");
    }
    str.append("]}");
    String res = encryptData(str.toString(), EncryptDecryptUtil.decrypt(secreteKey));
    logger.info("UploadLead. java :: LNO: 428 encrypted responses is : " + res);
    return new StreamResult(new ByteArrayInputStream(res.toString().getBytes()));
  }
    
  private boolean preValidation(UploadBean info) {
	  if(info.getCampaign_Name() != null && info.getAuth_Key() != null && info.getReference_Number() != null && info.getMobile_Number() != null && info.getSMS_Content() != null && 
			  info.getAuth_Key().length() > 0 && info.getCampaign_Name().length() > 0 && info.getReference_Number().length() > 0 && info.getMobile_Number().length() > 0 && info.getSMS_Content().length() > 0 &&
			    !info.getCampaign_Name().equalsIgnoreCase(" ") && !info.getAuth_Key().equalsIgnoreCase(" ") && !info.getReference_Number().equalsIgnoreCase(" ") && !info.getMobile_Number().equalsIgnoreCase(" ") && !info.getSMS_Content().equalsIgnoreCase(" "))
		  return true;
	  return false;
}

	private boolean validateRequest() {
		for (int i = 0; i < this.quickLead.size(); i++) {
			if (!this.quickLead.get(i).getAuth_Key().matches("[a-zA-Z0-9_-]*$")) {
				logger.warn("UploadLead. java :: LNO: 443 invalid Auth key");
				this.quickLead.get(i).toString();
				return false;
			}
			if (!this.quickLead.get(i).getCampaign_Name().matches("[a-zA-Z0-9_-]*$")) {
				logger.warn("UploadLead. java :: LNO: 448 invalid Campaign name");

				return false;
			}
			if (!this.quickLead.get(i).getReference_Number().matches("[a-zA-Z0-9_-]*$")) {
				logger.warn("UploadLead. java :: LNO: 453 invalid Reference Number");

				return false;
			}
			if (!this.quickLead.get(i).getMobile_Number().matches("[0-9]*$")) {
				logger.warn("UploadLead. java :: LNO: 458 invalid Mobile Number");

				return false;
			}
			if (!this.quickLead.get(i).getSMS_Content().matches("[a-zA-Z0-9_-]*$")) {
				logger.warn("UploadLead. java :: LNO: 463 invalid SMS Content");

				return false;
			}
		}
		return true;
	}
	
	private String getMessage() {
	  for (int i = 0; i < this.quickLead.size(); i++) {
			if (!this.quickLead.get(i).getAuth_Key().matches("[a-zA-Z0-9_-]*$")) {
				logger.info("UploadLead. java :: LNO: 474 invalid Auth key");
				this.quickLead.get(i).toString();
				return "invalid Auth key";
			}
			if (!this.quickLead.get(i).getCampaign_Name().matches("[a-zA-Z0-9_-]*$")) {
				logger.info("UploadLead. java :: LNO: 479 invalid Campaign name");

				return "invalid Campaign name";
			}
			if (!this.quickLead.get(i).getReference_Number().matches("[a-zA-Z0-9_-]*$")) {
				logger.info("UploadLead. java :: LNO: 484 invalid Reference Number");

				return "invalid Reference Number";
			}
			if (!this.quickLead.get(i).getMobile_Number().matches("[0-9]*$")) {
				logger.info("UploadLead. java :: LNO: 489 invalid Mobile Number");

				return "invalid Mobile Number";
			}
			if (!this.quickLead.get(i).getSMS_Content().matches("[a-zA-Z0-9_-]*$")) {
				logger.info("UploadLead. java :: LNO: 494 invalid SMS Content");

				return "invalid SMS Content";
			}
		}
		return "";
		
	}

	public StreamResult lmsQuickUploadLead() throws Exception {
	    StringBuilder str = new StringBuilder();
	    this.request = RequestUtil.getServletRequest();
	    str = str.append("{ \"response\" :[");
	    if (ValidatorUtil.isValid(this.request.getParameter("quickLeadId"))) {
	      JSONObject jsonObj = new JSONObject();
	      Integer leadId = Integer.valueOf(Integer.parseInt(this.request.getParameter("quickLeadId")));
	      logger.warn("UploadLead :: Quick Lead Id ::  " + leadId);
	      try {
	        ApplicationFormLead lead = this.commonService.getLeadById(leadId);
	        if (lead != null) {
	          this.taskExecutorService.SendingSMSForInfronics(Integer.valueOf(0), Integer.valueOf(3), lead, null);
	          this.callBackService.getcallBackService(lead);
	          jsonObj.put("status", "SUCCESS");
	          str.append(jsonObj.toString());
	        } 
	      } catch (NullPointerException e) {
		     this.json.put("error", "1");
		     logger.warn("lmsQuickUploadLead :: Exception Caught LNO: 521" + e);
		  } catch (Exception e) {
	        this.json.put("error", "1");
	        logger.warn("lmsQuickUploadLead :: Exception Caught LNO: 524" + e);
	      } 
	    } 
	    str.append("]}");
	    return new StreamResult(new ByteArrayInputStream(str.toString().getBytes()));
	  }

	public static SecretKey generateSecretKey(String password, byte [] iv) throws NoSuchAlgorithmException, InvalidKeySpecException {
	    KeySpec spec = new PBEKeySpec(password.toCharArray(), iv, ITERATION_COUNT, KEY_LENGTH); // AES-256
	    SecretKeyFactory secretKeyFactory = SecretKeyFactory.getInstance("PBKDF2WithHmacSHA1");
	    byte[] key = secretKeyFactory.generateSecret(spec).getEncoded();
	    return new SecretKeySpec(key, "AES");
	}	
	
	public static String encryptData(String data, String key)
			throws NoSuchPaddingException, NoSuchAlgorithmException, InvalidAlgorithmParameterException,
			InvalidKeyException, BadPaddingException, IllegalBlockSizeException, InvalidKeySpecException, UnsupportedEncodingException {

		SecureRandom secureRandom = new SecureRandom();
		byte[] iv = new byte[DEFAULT_GCM_IV_NONCE_SIZE_BYTES];
		secureRandom.nextBytes(iv);
		
		SecretKey secretKey = generateSecretKey(key, iv);

		Cipher cipher = Cipher.getInstance(CIPHER_ALGORITHM);
		GCMParameterSpec parameterSpec = new GCMParameterSpec(DEFAULT_GCM_AUTHENTICATION_TAG_SIZE_BITS, iv);

		cipher.init(Cipher.ENCRYPT_MODE, secretKey, parameterSpec);

		byte[] cipherText  = cipher.doFinal(data.getBytes("UTF-8"));

		byte[] encryptedData = new byte[iv.length + cipherText.length];
        System.arraycopy(iv, 0, encryptedData, 0, iv.length);
        System.arraycopy(cipherText, 0, encryptedData, iv.length, cipherText.length);

        return Base64.getEncoder().encodeToString(encryptedData);
	}

	public static String decryptData(String strToDecrypt, String key)
			throws NoSuchPaddingException, NoSuchAlgorithmException, InvalidAlgorithmParameterException,
			InvalidKeyException, BadPaddingException, IllegalBlockSizeException, InvalidKeySpecException, UnsupportedEncodingException {

		byte[] encryptedData = Base64.getDecoder().decode(strToDecrypt);
        byte[] iv = new byte[DEFAULT_GCM_IV_NONCE_SIZE_BYTES];
        System.arraycopy(encryptedData, 0, iv, 0, iv.length);
        
        SecretKey secretKey = generateSecretKey(key, iv);

		Cipher cipher = Cipher.getInstance(CIPHER_ALGORITHM);
		GCMParameterSpec parameterSpec = new GCMParameterSpec(DEFAULT_GCM_AUTHENTICATION_TAG_SIZE_BITS, iv);

		cipher.init(Cipher.DECRYPT_MODE, secretKey, parameterSpec);

		byte[] cipherText = new byte[encryptedData.length - DEFAULT_GCM_IV_NONCE_SIZE_BYTES];
        System.arraycopy(encryptedData, DEFAULT_GCM_IV_NONCE_SIZE_BYTES, cipherText, 0, cipherText.length);

        byte[] decryptedText = cipher.doFinal(cipherText);
        return new String(decryptedText, "UTF-8");

	}
}



