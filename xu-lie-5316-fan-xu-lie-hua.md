# 序列化/反序列化

> [https://www.cnblogs.com/traditional/p/11890639.html](https://www.cnblogs.com/traditional/p/11890639.html)

    type Test struct {
    	Name string
    	Age string `json:"age"`
    	sex string
    }
    func main()  {
    	a := Test{
    		Name: "name",
    		Age:  "aa",
    		sex:  "sex",
    	}
    	fmt.Println(a)
    	data, _ := json.Marshal(a)
    	fmt.Println(string(data))
    	var test Test
    	_ =json.Unmarshal([]byte(data), &test)
    	fmt.Println(test)
    }




