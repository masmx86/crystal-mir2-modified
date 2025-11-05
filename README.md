# crystal-mir2-modified
基于 [Crystal Mir2](https://github.com/Suprcode/Crystal)，添加了一些外挂辅助功能，主要用于单机自己玩 ![:-)](https://github.com/masmx86/crystal-mir2-modified/blob/main/smile.jpg)

##### 做过的修改：

1、解除了负重跑步限制

   ```
   Client\MirScenes\GameScene.cs
   private bool CanRun()
   ```
   ```
   Server\MirObjects\HumanObject.cs
   public virtual bool CanRun()
   public bool Run()
   ```

2、比奇和盟重的彩票员猜数字活动，无论输赢都会得到 1 千万金币

   ```
   Server\Envir\NPCs\BichonProvince\BichonWall\Lottery.txt
   Server\Envir\NPCs\MongchonProvince\MudWall\Lottery.txt
   ```

3、锁红锁蓝

   ```
   Server\MirObjects\HumanObject.cs
   public void ChangeHP()
   public void ChangeMP()
   ```

4、法师幻影术可以召唤最多 10 个分身（可以设置成无限制）

      原来的逻辑是法师没蓝以后分身会消失  
      锁蓝以后分身就会一直存在，无法消失  

   ```
   Server\MirObjects\HumanObject.cs
   private void Mirroring()
   ```
   
5、道士召唤术可以召唤最多 10 个宝宝（可以设置成无限制）

   ```
   Server\MirObjects\HumanObject.cs
   private void SummonSkeleton()
   private void SummonShinsu()
   ```

6、战士刀刀刺杀（未验证）

   ```
   Server\MirObjects\HumanObject.cs
   public void Attack() :Thrusting
   ```

7、仓库购买额外存储空间时间限制由 10 天改成 1 年

   ```
   Shared\Language.cs
   public static string ExtraStorage
   public static string ExtendYourRentalPeriod
   ```
   ```
   Server\MirObjects\PlayerObject.cs
   public void Chat() :ADDSTORAGE
   ```

12、物品持久保护（未验证）

   ```
   Server\MirObjects\HumanObject.cs
   private void DamageDura()
   public void DamageWeapon()
   public void DamageItem()
   ```
                     
                     
##### TODO：

1、道士自动换符、换毒药

2、自动显示、拾取超过一定等级的物品
