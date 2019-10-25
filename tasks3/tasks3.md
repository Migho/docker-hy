## TASK 3.1

Done. I think because I used Node from the start, my dockerfiles didn't have much to optimize.

## TASK 3.2

```
docker run -it -v $(pwd)/videos:/ylevideos asd <link>
```

## TASK 3.3

Done.

## TASK 3.4
Before:
```
Front: 161MB
Back: 59MB
```
After:
```
Front: 160MB
Back: 58.7MB
```
The difference is minimal, and seems like I have made a mistake. But I double checked it even with --no-cache and it seems to be valid.

## TASK 3.5



## TASK 3.6

I decided to little bit improve my only project where I now have dockerfile.

Before:
```
FROM node:10

COPY . .
RUN npm install

CMD ["npm", "start"]
```
After
```
FROM node:alpine

COPY . .
RUN npm install && \
    adduser app \
    --disabled-password \
    --gecos "" \
    --home "$(pwd)" \
    --no-create-home

USER app

CMD ["npm", "start"]
```

## TASK 3.7

I have seen Kubernetes in action in my work, but the only things I have done are deploying and checking the logs, the most basic things. I don't know why we are using kubernetes and why not something else. But I know that kubernetes is great in scaling the application and I think it's the biggest advantage in that.

Wikipedia says: "Kubernetes is platform for automating deployment, scaling, and operations of application containers across clusters of hosts". Now, automatic deployment is not a big thing, many systems can do that and are way easier to operate. I think the key thing why kubernetes is great is that automatic scaling. Consider you have an application which can have spikes in usage and can become under heavy load from time to time. Constantly reserving calculation power for this is usually expensive. With Kubernetes, we can set the system to scale the system on it's own whenever the system is under heavy load, for example by creating more containers. Kubernetes is also reliable and widely supported, and it's developed by Google. You should use Kubernetes whenever you need great scalability or at least some range of scalability.

## TASK 3.8

SKIPPED