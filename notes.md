### These are the notes of the developer Ryan Miller for the Fly.io coding sample:

Changes are in:

live/app_live/show.ex
- added deployment_status field to the socket to be accessed in the view (see line 14)
- added app_id because I thought this would be the ID needed to access the deployment status in graphQL. I am wrong about this apparently (see line 15, 25-26, 43-44)
- added private function called get_template_deployment_status 


lib/client/client.ex
- added some fields to access allocations data from graphQl
- added broadcast fields to enable LiveView reload (line 124, 230, 341, 343-346)

lib/fly_web/live/app_live/shot.html.heex
- added fields for instances. A very basic implementation (line 154-249)
- added fields for deployment status info (see comment on line 52)

