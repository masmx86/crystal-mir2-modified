# crystal-mir2-modified
基于 [Crystal Mir2](https://github.com/Suprcode/Crystal)，添加了一些外挂辅助功能，主要用于单机自己玩 ![:-)](https://github.com/masmx86/crystal-mir2-modified/blob/main/smile.jpg)

##### 文件中做过的修改：

###### 都在注释 [hack] 标签下

1、解除了负重跑步限制

   ```
   Client\MirScenes\GameScene.cs
   private bool CanRun()
   ```
   ```
   Server.Library\MirObjects\HumanObject.cs
   public virtual bool CanRun()
   public bool Run()
   ```

2、比奇和盟重的彩票员猜数字活动，无论输赢都会得到 1 千万金币

   ```
   Server\Envir\NPCs\BichonProvince\BichonWall\Lottery.txt
   Server\Envir\NPCs\MongchonProvince\MudWall\Lottery.txt
   ```

3、锁红锁蓝

      红保护线设置为 10~20%，永不死亡
      蓝保护线设置为 5~10%

   ```
   Server.Library\MirObjects\HumanObject.cs
   public void ChangeHP()
   public void ChangeMP()
   ```

4、法师幻影术可以召唤最多 10 个分身（可以设置成无限制）

      原来的逻辑是法师没蓝以后分身会消失  
      锁蓝以后分身就会一直存在，无法消失  

   ```
   Server.Library\MirObjects\HumanObject.cs
   private void Mirroring()
   ```
   
5、道士召唤术可以召唤最多 10 个宝宝（可以设置成无限制）

   ```
   Server.Library\MirObjects\HumanObject.cs
   private void SummonSkeleton()
   private void SummonShinsu()
   ```

6、~~战士刀刀刺杀（不是这里）~~

   ```
   Server.Library\MirObjects\HumanObject.cs
   public void Attack() :Thrusting
   ```

7、仓库购买额外存储空间时间限制由 10 天改成 1 年

   ```
   Shared\Language.cs
   public static string ExtraStorage
   public static string ExtendYourRentalPeriod
   ```
   ```
   Server.Library\MirObjects\PlayerObject.cs
   public void Chat() :ADDSTORAGE
   ```

12、物品持久保护

   ```
   Server.Library\MirObjects\HumanObject.cs
   private void DamageDura()
   public void DamageWeapon()
   public void DamageItem()
   ```

<<<<<<< HEAD
13、增加小极品物品掉落概率
=======
13、~~增加小极品物品掉落概率~~
>>>>>>> b525694d23c291e0b5373f0b7c6c4449ba1671b2
   ```
   Server.Library\MirEnvir\Envir.cs
   public void UpgradeItem()

   Server\Configs\RandomItemStats.ini

   ```

14、增加打怪爆率及掉落物品种类

   ```
   Server\Envir\Drops\*.txt
   ```                     
                     
##### TODO：

道士自动换符、换毒药

自动显示、拾取超过一定等级的物品，自动捡钱

自动喝药、自动喝灵符

自动修理装备

自动传送回城

自动挂机打怪

自动换装备

自动宠物回血

自动存取仓库
