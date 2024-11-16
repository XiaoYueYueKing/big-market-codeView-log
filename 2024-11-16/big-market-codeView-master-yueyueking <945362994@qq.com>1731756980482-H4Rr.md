根据您提供的日志信息，以下是对代码更改的总结和解释：

**主要更改**：

* **添加了RaffleActivityController和RaffleStrategyController**：这两个控制器分别处理抽奖活动和营销抽奖服务。它们实现了IRaffleActivityService和IRaffleStrategyService接口，并将请求参数转换为领域对象，调用领域服务，并将结果转换为响应对象。
* **添加了armory和strategyArmory方法**：这两个方法用于将活动配置和策略配置预热到缓存中，以便快速访问。
* **添加了queryRaffleAwardList和randomRaffle方法**：这两个方法分别用于查询奖品列表和执行随机抽奖。

**代码更改解释**：

* **RaffleActivityController**：
    * **armory方法**：该方法接收活动ID作为参数，调用activityArmory的assembleActivitySkuByActivityId方法将活动配置预热到缓存中，并调用strategyArmory的assembleLotteryStrategyByActivityId方法将策略配置预热到缓存中。
    * **draw方法**：该方法接收ActivityDrawRequestDTO对象作为参数，调用raffleActivityPartakeService的createOrder方法创建参与记录订单，调用raffleStrategy的performRaffle方法执行抽奖，并调用awardService的saveUserAwardRecord方法将中奖记录写入数据库。
* **RaffleStrategyController**：
    * **strategyArmory方法**：该方法接收策略ID作为参数，调用strategyArmory的assembleLotteryStrategy方法将策略配置预热到缓存中。
    * **queryRaffleAwardList方法**：该方法接收RaffleAwardListRequestDTO对象作为参数，调用raffleAward的queryRaffleStrategyAwardList方法查询奖品配置，并将结果转换为RaffleAwardListResponseDTO对象列表。
    * **randomRaffle方法**：该方法接收RaffleStrategyRequestDTO对象作为参数，调用raffleStrategy的performRaffle方法执行随机抽奖，并返回抽奖结果。

**总结**：

这些更改将抽奖活动和营销抽奖服务的接口实现与领域逻辑分离，并引入了缓存机制以提高性能。这些更改使代码更加模块化，易于维护和扩展。

**注意**：

* 代码中使用了JSON库进行JSON序列化和反序列化。
* 代码中使用了日志库进行日志记录。
* 代码中使用了异常处理机制来处理可能出现的错误。

希望这些信息对您有所帮助！