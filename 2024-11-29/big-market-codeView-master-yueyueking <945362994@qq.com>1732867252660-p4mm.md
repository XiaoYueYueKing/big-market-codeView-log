根据您提供的Git diff记录，以下是对代码变更的评审：

**1. application-dev.yml**

*   在`application-dev.yml`中添加了新的配置项`credit_adjust_success`，但没有提供具体的配置值。建议补充该配置项的值，以明确其用途和预期行为。

**2. raffle_activity_order_mapper.xml**

*   在`raffle_activity_order_mapper.xml`中添加了新的`select`和`update`语句，用于查询和更新订单信息。这些变更看起来是为了支持新的订单处理逻辑。
*   建议在添加新功能的同时，确保对现有功能的影响评估和测试。

**3. RaffleActivityAccountQuotaServiceTest**

*   在`RaffleActivityAccountQuotaServiceTest`中添加了新的测试用例`test_credit_pay_trade`，用于测试积分支付交易。
*   建议在添加新测试用例的同时，确保其他测试用例仍然有效，并覆盖所有新的功能。

**4. CreditAdjustServiceTest**

*   在`CreditAdjustServiceTest`中添加了新的测试用例`test_createOrder_pay`，用于测试积分调整成功后的订单出货。
*   建议在添加新测试用例的同时，确保其他测试用例仍然有效，并覆盖所有新的功能。

**5. CreateQuotaOrderAggregate**

*   在`CreateQuotaOrderAggregate`中添加了新的字段`payAmount`，用于存储订单支付金额。
*   建议在添加新字段的同时，确保相应的getter和setter方法也已添加。

**6. ActivityOrderEntity**

*   在`ActivityOrderEntity`中添加了新的字段`payAmount`，用于存储订单支付金额。
*   建议在添加新字段的同时，确保相应的getter和setter方法也已添加。

**7. ActivitySkuEntity**

*   在`ActivitySkuEntity`中添加了新的字段`productAmount`，用于存储商品金额。
*   建议在添加新字段的同时，确保相应的getter和setter方法也已添加。

**8. ActivityRepository**

*   在`ActivityRepository`中添加了新的方法`doSaveCreditPayOrder`和`updateOrder`，用于保存积分支付订单和更新订单状态。
*   建议在添加新方法的同时，确保相应的单元测试也已添加。

**9. CreditRepository**

*   在`CreditRepository`中添加了新的方法`saveUserCreditTradeOrder`，用于保存积分订单。
*   建议在添加新方法的同时，确保相应的单元测试也已添加。

**10. CreditAdjustSuccessCustomer**

*   在`CreditAdjustSuccessCustomer`中添加了新的方法，用于监听积分调整成功消息并进行订单出货。
*   建议在添加新功能的同时，确保消息监听和订单处理逻辑的正确性。

**总结**

总体而言，这些变更看起来是为了支持新的订单处理和积分调整功能。建议在进行代码部署前，确保：

*   所有新增功能都已通过单元测试和集成测试。
*   代码变更不会对现有功能造成负面影响。
*   代码符合项目代码风格和规范。

希望以上评审对您有所帮助。