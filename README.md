# collab-test-tool
This SDK based collab test tool have the ability to start a audio + video SIP call and join collab chat room. 
  - Test tool works only on Linux machine (webadm@web-testbox)
  - Go to `cd test_automation/collab/`

## Jenkins Tool Location:
- Jenkins: http://winsdkrosy.cp.local:8080/job/linuxCollabTestTool-trunk
- Download Links: http://winsdkrosy.cp.local:8080/job/linuxCollabTestTool-trunk/ws/core/cpcapi2_auto_tests/Linux/build/collab_test_tool

## There are 2 config files for this tool:
 - cpcapi2_collab_test_tool.config
 - vccsAccountSettings.json


 **NOTE:**
 Test tool is using Myles's provided test account on CCS3 production </b>

### In cpcapi2_collab_test_tool.config
- use collabLink = `https://collab.cloudprovisioning.com:443/join/MXHKYRRIGQ/sdktesttool.com`

### In vccsAccountSettings.json
                "group" : "sdktesttool.com",

                "userName" : "collabtest12",

                "password" : "j01$amazEng",

                "displayName" : "Collab Test",

                "wsSettings" : {
                    "webSocketURL" : "https://collab.cloudprovisioning.com:443/join",
                    "pingIntervalSeconds" : 50,
                    "initialRetryIntervalSeconds" : 5,
                    "maxRetryIntervalSeconds" : 800,
                    "certMode" : 1,
                    "logPayload" : true,
                    "backgroundSocketsIfPossible" : false,
                    "isLoginRequired" : true
                }
            }


