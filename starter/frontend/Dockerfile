FROM  public.ecr.aws/docker/library/node:18.14.2-alpine3.17

ARG REACT_APP_MOVIE_API_URL
ENV REACT_APP_MOVIE_API_URL=${REACT_APP_MOVIE_API_URL}
# ENV REACT_APP_MOVIE_API_URL="http://a095a9d88af8640b5bef84cd98f1e26d-1557655547.us-east-1.elb.amazonaws.com"

WORKDIR /app

# Copy dependdency files
COPY package*.json ./

# Install packages
RUN npm ci

# Copy code
COPY . .

# Build the app
RUN npm run build

# Expose the port used by the React app
EXPOSE 3000

# Start the React app when the container starts
CMD ["npm", "run", "serve"]