In the Phishing URL's data sets, The follwoing are 30 features. 

 having_IP_Address  URL_Length   Shortining_Service having_At_Symbol   double_slash_redirecting Prefix_Suffix  
 having_Sub_Domain   SSLfinal_State  Domain_registeration_length Favico Port HTTPS_token Request_URL  
 URL_of_Anchor Links_in_tags SFH Submitting_to_email Abnormal_URL Redirect  on_mouseover  RightClick  popUpWidnow 
 Iframe age_of_domain  DNSRecord  web_traffic  Page_Rank Google_IndexLinks_pointing_to_page Statistical_report 
 
 We have tried SVM and RF classifiers to train and predict the URL's as phishing or legitmate.    
 
 Among the 30 features, which features are relative importance with respect to predicitng  the target variable. 
 
 Randdom Forrest - scikit learn implementation proivdes the feature_importances_ variable which provides 
 features importance value which sums to1.0. The higher the value, the more important is the contribution of 
 the matching feature to the prediction function.
 
 Exercise:
 
 Find out the features which are importance in case of Phishing URL's dataset. 
 
 ( Refer Phishing-RF.ipynb , solution )
 
 
 
 print (rf.feature_importances_*100)
 
 [0.25627286  0.78662747  0.41844276  0.14726802  0.31589467  3.69688207
  5.64180775 27.7242637   1.81978371  0.38692895  0.28570932  0.69589994
  2.00110803 22.273091    3.98096606  0.57744725  0.56945432  0.37148832
  0.24691316  0.3530761   0.12476598  0.54829399  0.28658698  4.17971105
  2.74070317 12.91817475  2.92700777  1.3737365   2.02532499  0.32636931]
  
  SLfinal_State   = 27.7242637 %
  URL_of_Anchor   = 22.273091 %
  web_traffic     = 12.91817475 %
  
  It is very clear from the results that 3 features are making around 60% importannce in the clasifier to predict phising URL 
  and the rest are contributed to remaining ~40%.  
