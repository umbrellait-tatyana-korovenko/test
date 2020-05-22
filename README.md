# api-postman
Postman Collections of 9GAG APIs

## Intro
Leverage Postman Collections to make local and staging API testing faster for all clients

## Setup
1. Download and install Postman https://www.getpostman.com/downloads/
2. Press **Import** button in Postman and import Postman Collections (json file) under directory `/postman/collections` in this repo. https://learning.getpostman.com/docs/postman/collections/data-formats/#importing-postman-data. Currently, there are two collections:
    - 9GAG v2 API
    - Comment API
    - Notification API
    
3. Import Postman Environment (json file) under directory `/postman/environment` in this repo. Currently, there are two environments:
    - 9jokes
    - 9vm

## Staging
### 9GAG v2 API
1. After importing, expand the Collections menu to see different requests grouped by their usage
2. Set environment to 9jokes
2. `userToken` is necessary to make v2 API requests. Obtain it by either calling the guest token endpoint or by making login requests in Postman. The token obtained will be **saved automatically as an environment variable in Postman** and it will be attached to all subsequent API requests. It is not necessary to update it manually. By same logic, you can change the token by logging in another user

### Comment API
1. After importing, expand the Collections menu to see all requests
2. Set environment to 9jokes
3. `commentAuthHash` is required for certain Comment APIs. This will be saved automatically after logging in 9GAG from Postman

### Notification API
1. After importing, expand the Collections menu to see all requests
2. Set environment to 9jokes
3. `notiReadStateParams` is required for ReadState APIs. This will be saved automatically after logging in 9GAG from Postman

## Local Development (vm)
1. Configure Proxy in Postman Settings:
    - Global Proxy Configuration: `ON`
    - Proxy Type: `HTTP`
    - Proxy Server: `localhost:8118`
    - Proxy Bypass: `127.0.0.1, localhost`
2. Set environment to 9vm
3. Update environment variables as needed (e.g. local comment appId)

## Update Postman collections
1. In the event of new endpoints or API updates, make necessary changes to the Postman collection, and export the latest json file. https://learning.getpostman.com/docs/postman/collections/data-formats/#collections
2. Commit the change and push to origin

## Update Postman environment
1. Similar to collection updates, environment variables can be updated and exported as a json file https://learning.getpostman.com/docs/postman/collections/data-formats/#environments
2. Before committing the changes, ensure no sensitive information is included in the updated file

## Troubleshooting
1. If there are any issues regarding the collections or environments, feel free to ping web team and create a GitHub issue (with details) in this repo for follow-up
