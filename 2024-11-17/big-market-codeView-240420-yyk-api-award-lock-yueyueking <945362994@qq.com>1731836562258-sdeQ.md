根据提供的Git diff记录，以下是针对代码变更的评审：

### RaffleAwardListRequestDTO.java
- **变更**: 移除了`strategyId`字段，新增了`userId`和`activityId`字段。
- **评审**: 
  - **优点**: 新增`userId`和`activityId`字段使得请求更加明确，有助于后端根据用户和活动进行数据查询和处理。
  - **缺点**: 移除`strategyId`可能导致后端逻辑需要修改，确保其他依赖`strategyId`的代码能够正确处理。

### RaffleAwardListResponseDTO.java
- **变更**: 新增了`awardRuleLockCount`、`isAwardUnlock`和`waitUnLockCount`字段。
- **评审**:
  - **优点**: 新增字段提供了更多奖品解锁规则的信息，有助于前端展示和用户理解。
  - **缺点**: 需要确保前端正确处理这些新增字段，避免数据错误或展示异常。

### RedisClientConfig.java
- **变更**: 新增了对Redis编解码器的配置。
- **评审**:
  - **优点**: 使用JsonJacksonCodec进行序列化可以避免乱码问题，提高数据存储和读取的效率。
  - **缺点**: 需要确保所有使用Redis的地方都使用相同的编解码器，否则可能会导致数据不一致。

### raffle_activity_account_day_mapper.xml
- **变更**: 新增了`queryRaffleActivityAccountDayPartakeCount`查询方法。
- **评审**:
  - **优点**: 新增方法提供了查询用户参与次数的功能，有助于后端进行库存管理和活动规则控制。
  - **缺点**: 需要确保查询性能和数据库索引优化，避免查询效率低下。

### rule_tree_node_mapper.xml
- **变更**: 新增了`queryRuleLocks`查询方法。
- **评审**:
  - **优点**: 新增方法提供了查询奖品解锁规则的功能，有助于后端进行奖品解锁控制。
  - **缺点**: 需要确保查询性能和数据库索引优化，避免查询效率低下。

### LogicTreeTest.java
- **变更**: 移除了部分测试代码。
- **评审**:
  - **优点**: 移除冗余或无效的测试代码可以提高测试效率和代码可读性。
  - **缺点**: 需要确保移除的代码不会影响测试的全面性。

### RaffleActivityControllerTest.java
- **变更**: 新增了两个测试用例。
- **评审**:
  - **优点**: 新增测试用例可以更全面地测试抽奖活动的功能。
  - **缺点**: 需要确保测试用例的覆盖率和准确性。

### RaffleStrategyControllerTest.java
- **变更**: 新增了测试用例。
- **评审**:
  - **优点**: 新增测试用例可以更全面地测试抽奖策略的功能。
  - **缺点**: 需要确保测试用例的覆盖率和准确性。

### UserRaffleOrderEntity.java
- **变更**: 新增了`endDateTime`字段。
- **评审**:
  - **优点**: 新增字段可以记录订单结束时间，有助于后端进行订单管理和活动规则控制。
  - **缺点**: 需要确保字段的使用和更新逻辑正确。

### IActivityRepository.java
- **变更**: 新增了`queryRaffleActivityAccountDayPartakeCount`方法。
- **评审**:
  - **优点**: 新增方法提供了查询用户参与次数的功能，有助于后端进行库存管理和活动规则控制。
  - **缺点**: 需要确保查询性能和数据库索引优化，避免查询效率低下。

### IRaffleActivityAccountQuotaService.java
- **变更**: 新增了`queryRaffleActivityAccountDayPartakeCount`方法。
- **评审**:
  - **优点**: 新增方法提供了查询用户参与次数的功能，有助于后端进行库存管理和活动规则控制。
  - **缺点**: 需要确保查询性能和数据库索引优化，避免查询效率低下。

### IRaffleActivitySkuStockService.java
- **变更**: 新增了`queryRaffleActivityAccountDayPartakeCount`方法。
- **评审**:
  - **优点**: 新增方法提供了查询用户参与次数的功能，有助于后端进行库存管理和活动规则控制。
  - **缺点**: 需要确保查询性能和数据库索引优化，避免查询效率低下。

### RaffleActivityAccountQuotaService.java
- **变更**: 修改了`queryRaffleActivityAccountDayPartakeCount`方法。
- **评审**:
  - **优点**: 修改后的方法可以更准确地查询用户参与次数。
  - **缺点**: 需要确保修改后的方法与后端其他组件保持一致。

### RaffleFactorEntity.java
- **变更**: 新增了`end