package main

import (
	"fmt"
	"net/http"
	"time"
)

func main() {

	for i := 0; i < 100*10000; i++ {
		go func(i int) {

			response, err := http.Get("http://www.jl.10086.cn/JcaptchaCheckCode")
			if err != nil {
				fmt.Println(time.Now(), i, err)
				return
			}
			response.Body.Close()
			fmt.Println(time.Now(), i, "html")
		}(i)
		time.Sleep(time.Millisecond * 120)
	}

	time.Sleep(time.Hour)
}
