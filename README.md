**spiderDog**
**代码实例**
```java

@Source(url = "https://cj.sina.com.cn/article/detail/2475967382/318723?column=licai&ch=9")
public class Model {
    @Field(selector = "body > div.main-content.w1240 > h1")
    private String title;

    @Override
    public String toString() {
        return "Model{" +
                "title='" + title + '\'' +
                '}';
    }

    public String getTitle() {
        return title;
    }

    public void setTitle(String title) {
        this.title = title;
    }
}



 public static void main(String[] args) {

        DefaultSpider.createSpiderDog(null, new SpiderCall<Model>() {
            @Override
            public void onSuccess(Model model) {
                System.out.println(model.getTitle());
            }
        }, new Model())
                .run();
    }

     
```
