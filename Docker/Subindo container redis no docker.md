#docker #redis 


```d
version: "3"  
  
services:  
  redis:  
    image: redis  
    ports:  
      - "6379:6379"  
    volumes:  
      - redis_data:/data  
  
  app:  
    build: .  
    ports:  
      - "8000:8000"  
    depends_on:  
      - redis  
    environment:  
      - REDIS_HOST=redis  
  
volumes:  
  redis_data:
```