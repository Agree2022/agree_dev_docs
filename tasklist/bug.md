### BUG清单
+ ##### 1、前端用户管理userEdit.vue中，修改柜员号信息无法获取最新的数据
 需要注释掉 this.currentunit.tellerno = this.editForm.userCode
  ```
    //进入role选择的穿梭窗  item -> 部门信息
    modifyRoleRelation(item){   
        this.selectedRoles = this.currentunit.selectedRoles || [];
        //打开窗口
        this.innerDrawer = true; 

        //实际上设置默认柜员号为userCode【生产环境建议使用真实柜员号】
        // this.currentunit.tellerno = this.editForm.userCode;
    },
  ```

  ```
  {
  "result": true,
  "errorCode": "000000",
  "errorMessage": "处理成功",
  "content": {
    "data": [
      {
        #"payeeacc": "00000002",
        //"excpdealmsg": "差错处理成功",
        //"productcode": "IBPS",
        #"excpclass": "1",
        #"sendbankname": "绵阳市商业银行股份有限公司",
        //"busitype": "C200",
        //"busidealmsg": "核心扣账超时，同步状态失败",
        //"excpdate": "20210309",
        //"payername": "张三",
        //"excptype": "RA",
        #"busiacene": "IBPSSndPayServiceRA",
        //"excpserialno": "202103090000777730",
        //"excpdealbrno": "0200",
        //"packreqmsgid": "",
        //"autoflag": "",
        //"mbflag": "1",
        #"busichannelcode": "001",
        #"recvbank": "313736000019",
        //"returnmsg": "",
        #"currency": "CNY",
        //"agentserialno": "202103090000981021",
        //"busikind": "02001",
        #"accbrno": "",
        //"amount": "1000.01",
        #"scenecode": "SndCreditBusiProcess",
        //"payeename": "测试客户2",
        #"sendbank": "313659000016",
        "hostexcptype": "N",
        //"workdate": "20210309",
        #"busibrno": "1011",
        //"returncode": "",
        #"busitellerno": "80004",
        #"recvbankname": "曲靖市商业银行",
        //"excpdealcode": "A000000",
        "dcflag": "C",
        //"excpdealtellerno": "mock",
        //"payeracc": "000000001",
        #"servicecode": "IBPSSndPayService",
        //"excpstatus": "1",
        #"procnum": "2"
      }
    ],
    "page": {
      "sortStr": null,
      "total": 1,
      "pages": 1,
      "pageSize": 20,
      "pageNum": 1
    }
  },
  "errorTips": null
}

  ```