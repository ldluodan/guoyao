
```
  wx.request({
              url: loginUrl,
              method: 'POST',
              data: `{
                    "userId":${useridToken},
                    "type":"2", 	
                    "providerId":"1", 	
                    "simple":"0"
                  }`,
              success: res => {
                console.log(res)
                if (res.status == 500) {
                  console.log("登录失败或者超时")
                  util.showToastMsg('登录失败服务器请求没响应')
                  return
                }
                let userid = res.data.data.data.userInfo.userId
                let realName = res.data.data.data.userInfo.realName
                let logoFilename = res.data.data.data.userInfo.logoFilename
                // let genderName = res.data.data.empInfo.genderName
                wx.setStorageSync("empInfo", res.data.data.data.empInfo)
                wx.setStorageSync("userInfo", res.data.data.data.userInfo)
                wx.setStorageSync("userId", userid)
                wx.setStorageSync("logoFilename", res.data.data.data.userInfo.logoFilename)
                console.log(res.data.data)
                that.setData({
                  logoFilename: logoFilename,
                })
                app.globalData.realName = realName
                app.globalData.userId = userid
                console.log(app.globalData.realName)
                console.log(app.globalData.userId)
                if (that.userIdCallback) {
                  that.userIdCallback(res)
                }
                if (that.realNameCallback) {
                  that.realNameCallback(res)
                }
                // console.log(genderName)
                if (userid) {
                  //获取openiod
                  console.log("/user/binding進入接口")
                  wx.request({
                    url: `${app.globalData.residentUrl}/user/binding`,
                    method: 'POST',
                    // header: {
                    //   "content-type": "application/x-www-form-urlencoded",
                    // },
                    data: ` {
                            "userId":${app.globalData.userId},
	                          "openId":"${that.data.openid}",
	                          "providerId":1
                          }`,

                    success: res => {
                      if (!res.data.data) {
                        console.log('改账号没有绑定openid, 正在绑定')
                        // 绑定openid
                        wx.request({
                          url: loginUrl,
                          method: 'POST',
                          data: `{
                                  "userId":${useridToken},
                                  "type":"2", 	
                                  "providerId":"1", 	
                                  "simple":"0"
                                }`,
                          success: res => {
                            console.log('绑定openid成功')
                            console.log(res.data.status)
                            // if (res.data.status == 0){
                            //   util.showToastMsg('改用户或已绑定其它')
                            // }
                            app.globalData.isPendingPresShow = true
                            wx.switchTab({
                              url: '/pages/index/index',
                            })
                          }
                        })
                      } else if (res.data.data) {
                        console.log('已绑定openid')
                        app.globalData.isPendingPresShow = true
                        wx.switchTab({
                          url: '/pages/index/index',
                        })
                      }
                    }
                  })

                }
              }
            })
```
