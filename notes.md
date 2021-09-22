### These are the notes of the developer Ryan Miller for the Fly.io coding sample:

Changes are in:

live/app_live/show.ex
- added deployment_status field to the socket to be accessed in the view (see line 14)
- added app_id because I thought this would be the ID needed to access the deployment status in graphQL. I am wrong about this apparently (see line 15, 25-26, 43-44)
- added private function called get_template_deployment_status 


lib/client/client.ex
- added some fields to access allocations data from graphQl
- added broadcast fields to enable LiveView reload (line 124, 230, 341, 343-346)

lib/fly_web/live/app_live/show.html.heex
- added fields for instances. A very basic implementation (line 154-249)
- added fields for deployment status info (see comment on line 52)

### Other notes about the assessment 

Having never looked at Elixir/Phoenix before a week ago, I think I have a good grasp of the application. I really enjoyed working on this! Unfortunately the issues with deployment (unhealthy allocations) and accessing the deployment_status id from graphQL, stood in my way to acheive a completely finished product. Next steps for this app would definitely be implementing tests to ensure LiveView is updating exactly how I want it to 

### errors 

***v14 failed - Failed due to unhealthy allocations - no stable job version to auto revert to and deploying as v15 

### error logs

==> Failure #1

Instance
  ID            = e80d7fbd             
  Task          =                      
  Version       = 14                   
  Region        = sjc                  
  Desired       = run                  
  Status        = running              
  Health Checks = 1 total, 1 critical  
  Restarts      = 2                    
  Created       = 4m21s ago            

Recent Events
TIMESTAMP            TYPE             MESSAGE                                                         
2021-09-22T20:21:38Z Received         Task received by client                                         
2021-09-22T20:21:38Z Task Setup       Building Task Directory                                         
2021-09-22T20:21:42Z Started          Task started by client                                          
2021-09-22T20:23:00Z Restart Signaled healthcheck: check "0a33a4f86fa24b92a038e7a2786f7e82" unhealthy 
2021-09-22T20:23:04Z Terminated       Exit Code: 0                                                    
2021-09-22T20:23:04Z Restarting       Task restarting in 1.044465371s                                 
2021-09-22T20:23:11Z Started          Task started by client                                          
2021-09-22T20:24:28Z Restart Signaled healthcheck: check "0a33a4f86fa24b92a038e7a2786f7e82" unhealthy 
2021-09-22T20:24:33Z Terminated       Exit Code: 0                                                    
2021-09-22T20:24:33Z Restarting       Task restarting in 1.24096061s                                  
2021-09-22T20:24:39Z Started          Task started by client                                          
2021-09-22T20:25:56Z Restart Signaled healthcheck: check "0a33a4f86fa24b92a038e7a2786f7e82" unhealthy 

Recent Logs
2021-09-22T20:23:14Z [info] Reaped child process with pid: 568 and signal: SIGUSR1, core dumped? false
2021-09-22T20:23:31Z [error] Health check status changed 'warning' => 'critical'
2021-09-22T20:24:28Z [info] Shutting down virtual machine
2021-09-22T20:24:28Z [info] Sending signal SIGTERM to main child process w/ PID 510
2021-09-22T20:24:28Z [info] 20:24:28.370 [info] SIGTERM received - shutting down
2021-09-22T20:24:31Z [info] Main child exited normally with code: 0
2021-09-22T20:24:31Z [info] Starting clean up.
2021-09-22T20:24:34Z [info] Health check status changed 'critical' => 'passing'
2021-09-22T20:24:38Z [info] Starting instance
2021-09-22T20:24:38Z [info] Configuring virtual machine
2021-09-22T20:24:38Z [info] Pulling container image
2021-09-22T20:24:38Z [info] Unpacking image
2021-09-22T20:24:38Z [info] Preparing kernel init
2021-09-22T20:24:39Z [info] Configuring firecracker
2021-09-22T20:24:39Z [info] Starting virtual machine
2021-09-22T20:24:39Z [info] Starting init (commit: 50ffe20)...
2021-09-22T20:24:39Z [info] Preparing to run: `bin/fly start` as nobody
2021-09-22T20:24:39Z [info] 2021/09/22 20:24:39 listening on [fdaa:0:337a:a7b:ad1:e80d:7fbd:2]:22 (DNS: [fdaa::3]:53)
2021-09-22T20:24:39Z [info] Starting Elixir app: prod, DB=
2021-09-22T20:24:40Z [info] Reaped child process with pid: 547, exit code: 0
2021-09-22T20:24:41Z [info] 20:24:41.764 [info] Running FlyWeb.Endpoint with cowboy 2.9.0 at :::8080 (http)
2021-09-22T20:24:41Z [info] 20:24:41.766 [info] Access FlyWeb.Endpoint at http://crimson-wildflower-1711.fly.dev
2021-09-22T20:24:42Z [info] Reaped child process with pid: 568 and signal: SIGUSR1, core dumped? false
2021-09-22T20:24:53Z [error] Health check status changed 'warning' => 'critical'
2021-09-22T20:25:56Z [info] Shutting down virtual machine
2021-09-22T20:25:56Z [info] Sending signal SIGTERM to main child process w/ PID 510
2021-09-22T20:25:56Z [info] 20:25:56.639 [info] SIGTERM received - shutting down
2021-09-22T20:25:59Z [info] Main child exited normally with code: 0
2021-09-22T20:25:59Z [info] Starting clean up.
2021-09-22T20:26:01Z [info] Health check status changed 'critical' => 'passing'


### other 
I am really interested in working at Fly.io . I enjoyed my conversation with Michael and think I could be a great addition to the team. I enjoy learning lots of different technologies and thinking outside the box. I'd be really excited to work here and would work hard to become a senior engineer in no time :)