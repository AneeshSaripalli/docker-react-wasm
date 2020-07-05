FROM wasm-base
SHELL ["/bin/bash", "-c"] 
WORKDIR /app

ADD ./wasm/ ./wasm/

ADD package.json .
RUN npm update
RUN NODE_ENV=development npm install

ADD src src
ADD public/ public/

# RUN cd wasm && source ~/.cargo/env && wasm-pack build --debug --out-dir /app/public/wasm

# CMD ["npm", "start"]

ADD scripts/start.sh .
RUN chmod +x ./start.sh

ENTRYPOINT [ "./start.sh" ]