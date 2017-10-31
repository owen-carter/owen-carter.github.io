---
title: 前端面试题大全
date: 2017-10-15 15:11:06
tags: web manage
---

+ 假如有一道面试题
```ecmascript 6
import Router from 'router';
let router=new Router();

router.get('/user/list',(req,res)=>{
    let userList=[
        {
            name:'',
            age:12
        }
        ];
    res.json()
})
```

```ecmascript 6
class Ajax{
    constructor(){
        this.config={};
    }
    
    static getUserListFromMock(){
        return new Promise((resolve,reject)=>{
            let userList=[{userName:'ss',age:23}];
            setTimeout(()=>{
                resolve(userList)
            },1000)
        })
    }
    
    static getUserList(){
        return axios.get('/user/list')
    }
     
}

class App{
    constructor(){
        
    }
    
    async getuserList(){
        let res=await Ajax.getUserListFromMock();
        return res;
    }
    
    renderUserList(id,userList){
        let table=document.createElement('table');
        for(let user of userList){
            let tr=document.createElement('tr');
            let userName=document.createElement('td');
            userName.textContent(user.userName)
            let age=document.createElement('td');
            age.textContent(user.age)
            tr.appendChild(userName)
            tr.appendChild(age)
            table.appendChild(tr)
        }
        document.getElementById(id).appendChild(table)
    }
    
    run(){
       let userList= this.getuserList();
       this.renderUserList('body',userList)
    }
    
}

(new App()).run()
```