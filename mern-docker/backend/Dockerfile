FROM node:20-alpine3.18

# Create a new group named 'fullstack' and a new user named 'khantsithu' within that group
RUN addgroup fullstack && adduser -S -G fullstack khantsithu

# Set the user to 'khantsithu' for subsequent instructions
USER khantsithu

WORKDIR /app

COPY package*.json ./

# Change ownership of the /app directory to the 'khantsithu' user and 'fullstack' group
USER root
RUN chown -R khantsithu:fullstack .

# Change the user back to 'khantsithu'
USER khantsithu

RUN npm install

COPY . .

EXPOSE 8000

CMD npm start
