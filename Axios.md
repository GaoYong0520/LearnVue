        //两种发送POST请求的方式
        //方式一：发送URLSearchParams对象的数据
        let json = JSON.stringify(this.user);
        let params = new URLSearchParams();
        params.append('fuck', json);
        this.$http.post(url, params, config).then(
          (resp) => {
            console.log(resp.data);
            //console(resp.data);
          });

        //方式二：使用qs组件
        this.$http.post(url,qs.stringify({
          fuck: json
        }),config).then(
          (resp) => {
            console.log(resp.data);
          }
        )
