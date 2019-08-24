### retrofit
---
https://github.com/square/retrofit

https://square.github.io/retrofit/

```java
public interface GitHubService {
  @GET("users/{user}/repos")
  Call<List<Repo>> listRepos(@Path("user") String user);
}

Retrofit retrofit = new Retrofit.Builder()
  .baseUrl("https://api.github.com/")
  .build();

Call<List<Repo>> repos = service.listRepos("octocat");

@GET("users/list")

@GET("users/list?sort=desc")

@GET("group/{id}/users")
Call<List<User>> groupList(@Path("id") int groupId);

@GET("group/{id}/users")
Call<List<User>> groupList(@Path("id") int groupId, @Query("sort") String sort);

@POST("users/new")
Call<User> createUser(@Body User user);

@FromUrlEncoded
@POST("user/edit")
Call<User> updateUser(@Field("first_name") String first, @Field("last_name") String last);

@Multipart
@PUT("user/photo")
Call<User> updateUser(@Part("photo") REquestBody photo, @Part("description") RequestBody description);

@Headers("Cache-Control: max-age=640000")
@GET("widget/list")
Call<List<Widget>> widgetList();

@Header({
  "Accept: application/vnd.github.v3.full+json",
  "User-Agent: Retrofit-Sample-App"
})
@GET("users/{username}")
Call<User> getUser(@Path("username) String username);

@GET("user")
Call<User> getUser(@Header("Authorization") String authorization)

@GET("user")
Call<User> getUser(@HeaderMap Map<String, String> headers)

Retrofit retrofit = new Retrofit.Builder()
  .baseUrl("https://api.github.com")
  .addConverterFactory(GSonConverterFactory.create())
  .build();
  
GithubService service = retrofit.create(GithubService.class);
```

```gradle
implementation 'com.squareup.retrofit2:retrofit:(insert Latest version)'
```

```maven
<dependency>
  <groupId>com.squareup.retrofilt2</groupId>
  <artifactId>retrofit</artifactId>
  <version>(insert Latest version)</version>
</dependency>
```


