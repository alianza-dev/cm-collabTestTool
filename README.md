# collab-test-tool
This SDK based collab test tool have the ability to start a audio + video SIP call and join collab chat room. 
  - Test tool works only on Linux machine (webadm@web-testbox)
    - ssh webadm@web-testbox
    - Password : Ask Himani 
  - Go to `cd test_automation/collab/`

## Jenkins Tool Location:
- Jenkins: http://winsdkrosy.cp.local:8080/job/linuxCollabTestTool-trunk
- Download Link: http://winsdkrosy.cp.local:8080/job/linuxCollabTestTool-trunk/ws/core/cpcapi2_auto_tests/Linux/build/collab_test_tool

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

### Run Tests

Run collab_test_tool and added complete logs in collab.log file

``` ./collab_test_tool >> collab.log ```

**NOTE** 
If you get an error executable do not run give 777 permission to binary or related files 'chmod 777 collab_test_tool'

### Test Results

Success test logs looks like this if grep "\[\[" from complete logs

```
[webadm@web-testbox collab]$ cat collab.log | grep "\[\["
[[OK[ using xmpp proxy: imp.softphone.com]]]
[[OK[Done parsing config files]]]
[[OK[Account is registering]]]
[[OK[VCCS account seems registered okay]]]
[[OK[subscribed to the conference]]]
[2021-07-07 11:19:14.584](Debug)(ProbeTransactionState.cxx:246) 189686 ProbeTransactionState::processDnsResult(): tid=0956ddafbf2e5d14 [ Dns target=0.0.0.0 ] got DNS result: cs12.softphone.com --> [[ V4 216.93.246.144:5061 TLS target domain=cs12.softphone.com mFlowKey=0 ]]
[2021-07-07 11:19:14.585](Debug)(ProbeTransactionState.cxx:246) 189686 ProbeTransactionState::processDnsResult(): tid=354b403f872a15c9 [ Dns target=0.0.0.0 ] got DNS result: cs12.softphone.com --> [[ V4 216.93.246.144:5061 TLS target domain=cs12.softphone.com mFlowKey=0 ]]
[[OK[sip account seems registered okay]]]
[[OK[call in bridge]]]
[[OK[making an audio/video call...]]]
[[OK[conversation connected...]]]
[[OK[playing audio.....]]]
[[OK[participant  call status is IN_CONFERENCE]]]
[[OK[going to end the call-------------]]]
[[OK[conversation  ends]]]
[[OK[unsubscribed to the conference]]]
[[OK[conference ended]]]
```
