
```
{
  "pages": [
    "pages/index/index",
    "pages/login_signUp/identity_atication/identity_atication",
    "pages/my/900_setting/set_upsite/set_upsite",
    "pages/login_signUp/login/login",
    "pages/my/110_myPres/114_presCribing_prescription/114_presCribing_prescription",
    "pages/110_index_contuPrescri/116_pendingPresList/116_pendingPresList",
    "pages/my/010_myInfor/010_myInfor",
    "pages/login_signUp/signUp/signUp",
    "pages/login_signUp/complete_registration/complete_registration",
    "pages/login_signUp/complete_certification/complete_certification",
    "pages/my/310_myOrder_detail/320_myOrder_pay/320_myOrder_pay",
    "pages/login_signUp/upload_idcard/upload_idcard",
    "pages/110_index_contuPrescri/111_contuPrescri_main/111_contuPrescri_main",
    "pages/login_signUp/wxlogin/wxlogin",
    "pages/my/110_all_myprescriptions/110_all_myprescriptions/113_myallCollecPres",
    "pages/my/300_myOrder/300_myOrder",
    "pages/my/010_myInfor/011_Modification_unit/011_Modification_unit",
    "pages/my/110_myPres/113_myCollecPres/113_myCollecPres",
    "pages/my/310_myOrder/330_myrecentOrder/330_myrecentOrder",
    "pages/my/220_myAttention/220_myAttention",
    "pages/110_index_contuPrescri/118_presApplyDone/118_presApplyDone",
   
    "pages/my/900_setting/set_newsite/set_newsite",
    "pages/nearby/search/search",
    "pages/nearby/selectAddress/selectAddress",
    "pages/nearby/DetailsPharmacy/DetailsPharmacy",
    "pages/my/my",
    "pages/110_index_contuPrescri/114_contuPrescri_confirm/114_contuPrescri_confirm",
    "pages/my/310_myOrder_detail/330_myOrder_payment/330_myOrder_payment",
    "pages/my/310_myOrder_detail/310_myOrder_detail",
    "pages/my/010_myInfor/011_myInfor_address/011_myInfor_address",
    "template/200_recipe_template/200_recipe_template",
    "template/400_recipe_template/400_recipe_template",
    "pages/nearby/pharmacy/pharmacy",
    "pages/my/210_myFamily/210_myFamily",
    "pages/my/110_myPres/114_presCribing_collect/ 114_presCribing_collect",
    "pages/my/210_myFamily/212_myFamily_modify/212_myFamily_modify",
    "pages/my/220_myContact/220_myContact",
    "pages/my/220_myContact/222_myContact_modify/222_myContact_modify",
    "pages/my/220_myContact/221_myContact_add/221_myContact_add",
    "pages/110_index_contuPrescri/118_contacPeopList/118_contacPeopList",
    "pages/my/110_myPres/111_contactPeop/111_contactPeop",
    "pages/my/110_myPres/112_senior/112_senior",
    "pages/110_index_contuPrescri/112_contuPrescri_detail/112_contuPrescri_detail",
    "pages/my/110_myPres/112_contactPeop_pres/112_contactPeop_pres",
    "pages/my/210_myFamily/211_myFamily_addMember/211_myFamily_addMember",
    "pages/my/900_setting/900_setting",
    "pages/my/900_setting/set_site/set_site",
    "pages/110_index_contuPrescri/117_presApplyDone/117_presApplyDone",
    "pages/110_index_contuPrescri/115_contuPrescri_pay/115_contuPrescri_pay",
    "pages/110_index_contuPrescri/113_contuPrescri_apply/113_contuPrescri_apply",
    "pages/my/110_myPres/114_contactPeop_collecPres/114_contactPeop_collecPres",
    "pages/my/911_setting_healthbank_modify/911_setting_healthbank_modify",
    "pages/my/910_setting_healthbank/910_setting_healthbank",
    "pages/index/400_drugstore/420_drugstore_detail/420_drugstore_detail",
    "pages/index/400_drugstore/410_drugstore_list/410_drugstore_list",
    "pages/index/400_drugstore/400_drugstore",
    "template/100_drug_template/120_drugstore_template/120_drugstore_template",
    "template/100_drug_template/110_druglist_template/110_druglist_template",
    "pages/login_signUp/findPassword/findPassword",
    "pages/login_signUp/userInforMange/userInforMange",
    "pages/login_signUp/modifyInitialPassword/modifyInitialPassword",
    "pages/nearbyMedicinen/nearbyMedicinen",
    "pages/my/110_myPres/113_senior/113_senior",
    "pages/110_index_contuPrescri/prescriptionFelling/112_contuPrescri_detail",
    "pages/message/message",
    "pages/message/consultationChat/consultationChat",
    "pages/message/details/details"
  ],
  "window": {
    "backgroundTextStyle": "light",
    "navigationBarBackgroundColor": "#4D66FD",
    "navigationBarTitleText": "WeChat",
    "navigationBarTextStyle": "white",
    "backgroundColor": "#f5f5f5"
  },
  "tabBar": {
    "color": "#6e7586",
    "selectedColor": "#4d66fd",
    "borderStyle": "#dadada",
    "backgroundColor": "#FFFFFF",
    "list": [
      {
        "text": "首页",
        "pagePath": "pages/index/index",
        "iconPath": "images/index.png",
        "selectedIconPath": "images/index-actived.png"
      },
      {
        "text": "消息",
        "pagePath": "pages/message/message",
        "iconPath": "images/message.png",
        "selectedIconPath": "images/message-actived.png"
      },
      {
        "text": "我的",
        "pagePath": "pages/my/my",
        "iconPath": "images/my.png",
        "selectedIconPath": "images/my-actived.png"
      }
    ]
  },
  "networkTimeout": {
    "request": 100000,
    "connectSocket": 80000,
    "uploadFile": 60000,
    "downloadFile": 10000
  },
  "plugins": {
    "WechatSI": {
      "version": "0.2.2",
      "provider": "wx069ba97219f66d99"
    }
  },
  "permission": {
    "scope.userLocation": {
      "desc": "导航"
    }
  },
  "navigateToMiniProgramAppIdList": [
    "wx687c8bbada3340c3",
    "wx634809b495946672"
  ]


}
```

```
  obtn: function (e) {
    console.log(e);
    var id = e.currentTarget.dataset.id;
    if (id == 0) {
      wx.switchTab({
        url: '/pages/index/index',
      })
    } else if (id == 1) {
      wx.switchTab({
        url: '/pages/my/my',
      })
    }
  },
```
