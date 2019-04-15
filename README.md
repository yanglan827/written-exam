# 笔试题  

请完成以下笔试题，可以使用自己擅长的语言来编写，通过 github pull request 提交代码。

1. 编写一个递归版本的 reverse(s) 函数(或方法),以将字符串s倒置。
    // 非递归
    function handereverse(s) {
        // 转化为数组
        let arr = s.split('');
        let length = arr.length;
        if (len > 1) {
            for (let i = 0; i < (length - 1) / 2; i++) {
                lettemp = arr[i];
                arr[i] = arr[length - 1 - i];
                arr[length - 1 - i] = temp;
            }
        }
        let string=arr.join('');
        return string;
    }

// 递归：一
function reverse(arr,length){
    if(length>1){
        for(let i=0;i<length-1;i++){
            let temp=arr[i+1];
        }
        length--;
        reverse(arr,length);
    }
    return arr;
}
function handr(s){
    let arr=s.split('');
    let length=arr.length;
    return reverse(arr,length).join('');
}

//递归二：
 function reverse2(arr,length,a){
     if(length>=1){
         let temp =arr.shift();
         a[length-1]=temp;
         len=len-1;
         reverse(arr,len,a);
     }
     return a;
 }
 function hand2(s){
     let arr=s.split('');
     let length=arr.length;
     let a=[];
     let answer=reverse(arr,length,a).join('');
     return answer;
 }

2. 编写程序 expr，以计算从命令行输入的逆波兰表达式的值，其中每个运算符或操作数用一个单独的参数表示。例如，命令
expr 2 3 4 + *
expr=(arr=[])=>{
    if(!arr)return 0;
    var tempArr=arr.split('');
    var elems=[];
    let item='';
    while(item=tempArr.shift){
        if(!isNaN(+item)){
            elems.push(+item)
        } else{
            var res=count(item,elems.pop,elems.pop)
            elems.push(res)
        }
    }
}
count =(opera,num1,num2)=>{
    switch(opera){
        case '+':
        return num2+num1
        case '-':
        return num2-num1
        case '*':
        return num2*num1
        case '/':
        return num2/num1
    }
}
3. 用归并排序将3，1，4，1，5，9，2，6 排序。
mergeSort=()=>{
    var arr=[3,1,4,1,5,9,2,6];
    if(arr.length===1)
    return arr;
    var mid=(a.length/2),left=a.slice(0,mid),right=a.slice(mid);
    return merge(mergeSort(left),mergeSort(right));
}
merge=(left,right)=>{
    while(left.length && right.length){
        if(left[0]<right[0])
        tem.push(left.shift());
        else
        tem.push(right.shift());
    }
    return tmp.concat(left,right);
}
4. 对下面的 json 字符串 serial 相同的进行去重。

```javascript
  [{
    "name": "张三",
    "serial": "0001"
  }, {
    "name": "李四",
    "serial": "0002"
  }, {
    "name": "王五",
    "serial": "0003"
  }, {
    "name": "王五2",
    "serial": "0003"
  }, {
    "name": "赵四",
    "serial": "0004"
  }, {
    "name": "小明",
    "serial": "005"
  }, {
    "name": "小张",
    "serial": "006"
  }, {
    "name": "小李",
    "serial": "006"
  }, {
    "name": "小李2",
    "serial": "006"
  }, {
    "name": "赵四2",
    "serial": "0004"
  }];
```
代码：  handArr = () => {
        let arr = [{
            "name": "张三",
            "serial": "0001"
        }, {
            "name": "李四",
            "serial": "0002"
        }, {
            "name": "王五",
            "serial": "0003"
        }, {
            "name": "王五2",
            "serial": "0003"
        }, {
            "name": "赵四",
            "serial": "0004"
        }, {
            "name": "小明",
            "serial": "005"
        }, {
            "name": "小张",
            "serial": "006"
        }, {
            "name": "小李",
            "serial": "006"
        }, {
            "name": "小李2",
            "serial": "006"
        }, {
            "name": "赵四2",
            "serial": "0004"
        }];
      let newArr=arr.filter(function(element,index,self){
          return self.indexOf(element)===index;
      });
    }
5.把下面给出的扁平化JSON数据用递归的方式改写成组织树的形式

```javascript
  [
    {
      "id": "1",
      "name": "中国",
      "code": "110",
      "parent": ""
    },
    {
      "id": "2",
      "name": "北京市",
      "code": "110000",
      "parent": "110"
    },
    {
      "id": "3",
      "name": "河北省",
      "code": "130000",
      "parent": "110"
    },
    {
      "id": "4",
      "name": "四川省",
      "code": "510000",
      "parent": "110"
    },
    {
      "id": "5",
      "name": "石家庄市",
      "code": "130001",
      "parent": "130000"
    },
    {
      "id": "6",
      "name": "唐山市",
      "code": "130002",
      "parent": "130000"
    },
    {
      "id": "7",
      "name": "邢台市",
      "code": "130003",
      "parent": "130000"
    },
    {
      "id": "8",
      "name": "成都市",
      "code": "510001",
      "parent": "510000"
    },
    {
      "id": "9",
      "name": "简阳市",
      "code": "510002",
      "parent": "510000"
    },
    {
      "id": "10",
      "name": "武侯区",
      "code": "51000101",
      "parent": "510001"
    },
    {
      "id": "11",
      "name": "金牛区",
      "code": "51000102",
      "parent": "510001"
    }
  ];
```
代码：  var tree = [
        {
            "id": "1",
            "name": "中国",
            "code": "110",
            "parent": ""
        },
        {
            "id": "2",
            "name": "北京市",
            "code": "110000",
            "parent": "110"
        },
        {
            "id": "3",
            "name": "河北省",
            "code": "130000",
            "parent": "110"
        },
        {
            "id": "4",
            "name": "四川省",
            "code": "510000",
            "parent": "110"
        },
        {
            "id": "5",
            "name": "石家庄市",
            "code": "130001",
            "parent": "130000"
        },
        {
            "id": "6",
            "name": "唐山市",
            "code": "130002",
            "parent": "130000"
        },
        {
            "id": "7",
            "name": "邢台市",
            "code": "130003",
            "parent": "130000"
        },
        {
            "id": "8",
            "name": "成都市",
            "code": "510001",
            "parent": "510000"
        },
        {
            "id": "9",
            "name": "简阳市",
            "code": "510002",
            "parent": "510000"
        },
        {
            "id": "10",
            "name": "武侯区",
            "code": "51000101",
            "parent": "510001"
        },
        {
            "id": "11",
            "name": "金牛区",
            "code": "51000102",
            "parent": "510001"
        }
    ];

    transDate = (tree, idstr = 'id', pidstr = 'parent') => {
        let result = [], temp = {};
        for (i = 0; i < tree.length; i++) {
            temp[tree[i][idstr]] = tree[i];
        }
        for (j = 0; j < tree.length; j++) {
            tempVp = temp[tree[j][pidstr]];
            if (tempVp) {
                if (!tempVp["nodes"]) tempVp["nodes"] = [];
                tempVp["nodes"].push(tree[j]);
            } else {
                result.push(tree[j]);
            }
        }
        return result;
    }
