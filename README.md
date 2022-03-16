# Instagram clone with Vue 3 and Nest

### Video  
TODO

### Project structure
for a quick understanding of project structure you can look at frontend models (frontend/src/models) or backend modules and their entities (backend/src/modules)

### Stack
#### Frontend

1. Vue 3
2. Vuex
3. Typescript
4. Quasar
5. Vue i18n
6. other - date-fns, some lodash functions, eslint + tslint + prettier

#### Backend

1. Node.js (Nest.js)
2. Typescript
3. PostgreSQL + TypeORM
4. AWS S3 (Amazon Simple Storage Service)

#### Other

Github actions CI pipeline

### App Features

❌ === not implemented yet  
✨ === TODO idea. it seems that it won't be implemented but there were some plans


#### Global
- English lanugage (wow!)
- User notifications (Post like, Comment like, User followed)
- Remove notificiation if user unliked/unfollowed
- User following system

#### Auth
- Login / Register / Forgot password
- OAuth with Google / Github
- Unique username / email
- Send email verification mail
- Automaticly redirect to requested page after login (/auth?redirect=/profile/1)
- JWT access (1d exp) and refresh (30d exp) tokens, auto relogin if access token expired 

#### Feed
- View all recent posts from friends (push / fan-out-on-write)
- View own new posts (<24h) on top before friends feed
- Remove friend's post from feed after user has seen it ✨
- View all recent based on their naive calculated score (likes, comments, views number) after friends feed ❌
- Use pull / fan-out-on-read feed for celebrities (100000+ subscribers) ✨
- Feed infinite scroll with [vue-observe-visibility](https://github.com/Akryum/vue-observe-visibility)
- Search users, search tags
- User suggestions in sidebar who follows you / followed by who you follow / new to instagram
##### Post
- Posts CRUD
- Images support. Dragndrop or browse image to upload
- Videos support. Dragndrop or browse video to upload ✨
- Image crop with [vue-cropperjs](https://github.com/Agontuk/vue-cropperjs#readme)
- Image aspect ratio (1:1, 4:5, 16:9, original)
- Image filters
- Tags system and tag suggestion
- Dbclick to like post (with cool animation haha) or like with button
- Show users who liked this post
- Comments CRUD
- Like comment
- Report post
- Comment system with infinity reply nesting with path enumeration / materialized path | look bugs section (1)
- Share to users in messanger ✨
- Bookmark ✨
##### Story
- Story CR✨U✨D✨
- Drawing canvas with [vue-drawing-canvas](https://github.com/razztyfication/vue-drawing-canvas)
- Implement smart eraser (erase only user drawings) ✨

#### Messenger (?)

#### Profile page
- View all own photos/videos
- View posts, followers and followed number
- Follow/unfollow if not own page
- Edit info - change username / name / email (✨) / bio etc...
- Upload user avatar (store in AWS S3, compression with [sharp](https://github.com/lovell/sharp))
- Upload gif avatar ✨

### Known bugs
1. Can't load author relation in comment replies (posts.service.ts, line 172) and need to fix update/delete and correct create reply saving in frontend
2. Missing pagination in profile, post likes and somewhere else
3. Story drawing canvas incorrect markup if 16:9 image

### Install  
1. Clone project  
2. Terminal 1 - "docker compose up"  
3. Terminal 2 - "yarn global add @quasar/cli" and "cd .\frontend\" and "quasar dev"  
4. Terminal 3 - "cd .\backend\" and "yarn start:dev" 
5. Don't forget to create new server (Object => Create => Server) and then database (instagram) in pgadmin (localhost:8082). small tip: in server connection field enter: host.docker.internal
6. do you like starsssss? 🤩😊 anyway, glad to any PRs  


