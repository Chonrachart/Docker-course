FROM node:22-alpine AS build
WORKDIR /app
COPY package*.json .
RUN npm ci 

COPY src src
COPY tsconfig.json tsconfig.json

RUN npm run build

FROM gcr.io/distroless/nodejs22
WORKDIR /app
#COPY package*.json .  not need anymore
#RUN npm ci  not need anymore
#COPY from the previous stage 
COPY --from=build /app/node_modules node_modules 
COPY --from=build /app/dist dist


ENV PORT=3000

# node is default by distroless image so just pass file to execute
CMD [ "dist/index.js" ]






