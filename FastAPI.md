
1. **Create Routers**: They allow you to group related routes together. You can create routers for different functional areas or resources within your [[API]].
    
    ```python 
    app = FastAPI()
	router = APIRouter()
    ```
    
2. **Define Routes Within Routers**: That is done so you could put your code outside main.py and have routers with some prefixes

    ```python 
    @router.get("/items/") 
    def get_items():     
		# Your logic here    
		pass
		
	app.include_router(router, prefix="/my-prefix")
		```

3. Dependency injection with Depends().
```python
def is_paid_user(user: UserInDB = Depends(get_current_user)):
    if user.api_key != "testapikey":
        raise HTTPException(
            status_code=status.HTTP_403_FORBIDDEN,
            detail="You need a valid API key to access this endpoint"
        )
    return user

@app.get("/generate-random-number/")
def generate_random_number(current_user: UserInDB = Depends(is_paid_user)):
    random_number = random.randint(1, 100)
    return {"random_number": random_number}
```

4. Middleware. Catch all requests and process them (useful for authentication)
```python
@app.middleware("http")
async def custom_middleware(request: Request, call_next):
    # Do something before the request is processed
    response = await call_next(request)
    # Do something after the response is generated
    return response
```
