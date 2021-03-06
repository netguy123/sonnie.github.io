# 工作台需求表

## WOS

### 前端

- [ ] 引文清单切换显示 总引、自引、宽松和严格他引
- [ ] 标题样式修改，TC/[实际引文数] 上传按钮
- [ ] Not found 后加入上传按钮
- [ ] 自助服务：统一认证登录后两个入口，一个是打开自己的论文库，一个是输入他人的工资号和姓名，打开其论文库；勾选文章后加入“购物车”；手动上传WOS号后，实时检索给出文章信息，确认后加入购物车（并加入论文库）；结算即提交到下载表，等同步或下载结束后，可发邮件通知其已经完成（可以动态显示流程），在工作时间到馆盖章。
- [ ] 每次更新完某篇文章的引文信息后，把更新的结果以某种方式显示出来，比如：新增 N 篇；未更新 X 篇。后面这个尤其重要，未更新的，很可能已经不是它的引文了，接下来给出一个界面，可以让你们核实后，决定是否解除引文关系
- [ ] 思考：如何判断订单的状态？关键是要能判断是否更新完毕，这里的问题在于，下载列表不允许ut重复，那么后面订单里的ut就无法加入下载列表，它的状态就只能依赖在列表中的。除非不同订单的ut可以都进入下载列表（修改表结构）。如果每篇文章的更新状态都判断结束，那么就认为订单完成。
- [ ] wos显示自己最近的申请单简介：申请时间、申请人、文章数、统计类型，可点击查看
- [ ] 在检索框里输入姓名、工资号或邮箱，自动完成，下拉点击打开
- [x] 导出wos号：点选文章即“加入购物车”，然后选择1）导出wos号 2）统计——选择统计方式，最后提交
- [ ] 引用详单中，地址+通讯地址信息 可选择显示或隐藏
- [ ] 上传文件后，文章选中状态保存到SESSION里
- [ ] 上传的文章优先级高，同作者的其他文章不同时更新，或优先级更低
- [ ] 加入下载列表时，根据文章上次的更新时间来判断。如果是上周六之后更新的，则已经是最新数据，无需加入！
- [ ] 更新后给出更新的详情，提示哪些文章没有被更新到，进而可以去解除关系！
- [ ] 打开论文库后显示文章的最新更新时间
- [ ] 打开论文库后文章可以手动更新
- [x] 唯一第一作者、共同第一作者、唯一通讯作者、共同第一作者
- [ ] 加入论文库时，根据wos号对应的文章（很可能已经保存在本地了）的author信息预判断是否本人的文章。
- [ ] 切换显示“所有人的下载列表”，默认只显示自己的
- [ ] 加一个被引频次的文章篇数统计功能，方便计费，分别统计：0次，？篇；1-50次，？篇；51-100次，？篇；101-300，？篇；300次以上，？篇。校内：收录5元/篇，宽松引用是上面的标准（严格他引加倍）。校外：基费50  收录20/篇，引用费用分别是校内的2倍
- [ ] 根据输入的姓名自动填充到作者字段，允许修改
- [ ] 保存统计的勾选类型！！只保留咨询部馆员的统计
- [ ] 检索报告自动生成
- [ ] 显示的表格里有null
- [ ] 论文库列表可以勾选要显示的字段 http://datatables.club/example/user_share/custom_hide_filter_column.html
- [ ] 打开每个作者的所有历史订单，要保存历史订单到单独的表！
- [ ] 打开某个历史订单，追加上传成为新订单
- [ ] 为了显示某篇文章的被引用趋势，考虑把TC单独做表，跟日期相关。定期获取lastUpdated，然后同步TC后写入该表。
- [ ] 等级聘用等作为统计分类，允许手动输入和下拉菜单。归纳“统计规则”，与每个分类进行关联。传参数时，把分类名称和勾选的内容都传过去。
- [ ] 提交后即把勾选情况保存下来，这样在打开论文库时仍然可以看到
- [ ] 打开论文库时显示not found
- [ ] 加入 not found 时，被引频次不应该有值
- [ ] 用session保存馆员的ip、名字等等信息，这样就不用传参数了？
- [ ] datatable: row selection 貌似不难；rowID用get方法给open...php传参，返回json再用dt处理
- [ ] 去掉not found加入后的弹窗报警
- [ ] 原文的upload以及局部刷新，注意要传org='USTC'
- [ ] 在论文库打开状态时，可以选择不统计，而直接保存作者类型
- [ ] 一般出版年里会给出具体年月甚至到日，就是按照这个倒序来排的，那些只给出年的就排在同一年的最后面
- [ ] 排序：
- [ ] 加入论文库的代码合并到打开论文库
- [ ] 保存申请单里的单位信息，同时修改ajaxupload里 isUSTC
- [ ] jquery中多处地方反复获取元素的值，能否共用？
- [ ] 排除指定作者的引用
- [ ] 显示引文清单时增加一个中间步骤：只显示少量的元数据，以及所有引文的作者名，交互式确认后提交才生成原有格式的清单，默认全选。
- [ ] 输出列表：筛选显示字段，切换显示引文清单
- [ ] url压缩编码、解码
- [ ] 用 mysql 的 create procedure 来优化 insert or select （插入后获得id，如果存在则获得id）这样的请求
- [ ] 侧边栏信息输出哪些？
- [ ] refworkbench导航包括：
- [ ] 数据维护：显示统计数据；搜索本地的文章元数据，结果列表，内容页显示
- [ ] 引文列表，操作：1) 解除引文关系 2) 从数据库中直接删除（有的文章不再存在于wos了）
- [ ] 作者以及论文库管理：另外有个系统来登录、管理，包括删除不属于他的文章
- [ ] 解除引文关系：delete from reference2 where ut_orig='000347542500012' and ut_ref not like '000362083700006';
- [ ] 对下载列表的干预，友好
- [x] 原文列表分页，并可以保存内容用datatable实现
- [x] 定时刷新论文列表，以更新论文库状态
- [x] 每个馆员如何知道更新进度？首先要看订单，知道更新的是哪个作者，然后查看下载列表里该作者的ut数量；用ajax定期动态获取数据。这里的问题在于：原先的订单是针对统计的，也就是说，“加入论文库”这个操作并没有相应的日志。
- [ ] ajaxupload里的success代码共用
- [ ] 根据不同的文件名，调用不同的js文件
- [ ] 高亮显示：引文的作者名是申请人作者名的前N个字符，如zhang a < zhang ab < zhang abc
- [ ] 用like '%;name_au;%' 的方法排查引用
- [ ] 默认是”校内“，显示为 工资号；选择”校外“后，改显示为备注
- [ ] applicant.php里返回applicant_id的篇数
- [ ] 上传找不到的，则自动加入downlist!
- [ ] 近5年（year-5）的数据切换显示
- [ ] 原文列表：全选、反选；禁止排序；显示年份
- [ ] 由于原文可能很长，考虑以弹窗的形式显示检索报告
- [ ] 标题可能不一致，因此暂时不做：前端弹窗输入标题列表，异步提交给 get_fileinfo_by_title.php，处理返回xml，原文列表同样显示在右侧，标记没找到的。 考虑删除题名前的编号。
- [ ] @app: 联合article和reference，读取某个ut_orig对应的引文的作者和ref_id

### 后台

- [ ] 根据last_update同步更新科大的文章
- [ ] Ei、CSCD文章单篇下载
- [ ] 测试直接根据truecount判断是否需要更新
- [ ] progress改为+之前，考虑last_update
- [ ] 当把一篇文章disable(enable=0)后，它在引文关系表里的所有数据应删除（即它引用和被引的关系）
- [ ] 根据科大的检索式得到所有的UT，一次性下载后，每周同步1到3次
- [ ] 如果遇到API无响应，则不修改progress
- [ ] 无论如何，只要不是同一个用户添加的ut，都加入下载列表进行排队，即键值是(ut,op_ip)，这样可以避免出现，在一个线程里已经排队更新的，还不如后加入列表的、另一个线程里的先更新完。当一个ut开始更新时，检查列表里是否有其他重复的ut，如果有，则修改其状态为同步！更新完后删除相同的ut
- [ ] 闲时下载：如果下载列表中的数据不超过M个（比如20），则从优先级0中选取M个改为优先级2：update article_downlist set priority=2 where ut in (select t.ut from (select * from article_downlist where priority=0 limit 0,20) as t);
- [ ] proc::daemon把下载脚本变成守护进程
- [ ] update脚本的SQL需要优化，否则5w条UT加入后CPU=100%！！
- [ ] 根据元数据找到所有的article，如果没有org则添加，更新所有的AR
- [ ] 为了不影响app的速度，另外找台93的机器专门用来下载
- [ ] 需要update的，根据lastUpdate判断是否有必要；或者在加入前判断
- [ ] downlist要把meta_only放最后，优先其他的
- [ ] download的coro
- [ ] 定期：引文完备性检查，所有存在于引文关系中但缺失文章信息的，自动加入downlist
- [ ] 定期：按照订单下载更新或下载不存在UT，其标记应该有别于update
- [ ] 定期：wos首页->wos，更多设置里的最新更新日期
- [ ] 整合import进入down_articles.pl，org=USTC需要某种方式标记！
- [ ] 更新程序中，除了得到原文的信息、线程代码以外，其他的应可以并入下载程序。因此对down_article增加update参数。
- [ ] 确定更新范围：如org=USTC的文章和org=USTC的applicant的文章
- [ ] 除了org以外，考虑创建一个新的字段，以扩大“机构知识库”的概念。
- [ ] USTC的文章现为手动导入，一旦要手动上传，则需要表单里给出单位，并在保存原文信息时加参数 org
- [ ] 表设置外键以保证数据一致？
- [ ] 根据RSS改写update.pl，以定期执行任务
- [ ] 定期：每天进行分库检索，排序后得到最新的前N条记录（根据差值），导入；每周进行全库检索，得到所有文章的全记录，导入后下载所有引文的全记录
- [ ] article表是否要只保存全记录里用于检索的必要字段，其他字段另外建表保存？
- [ ] 挖掘数据，根据research id，email，author等信息分析，建立 salaryno 与这些信息的对应关系。
- [ ] 实时计算，无需写表
- [ ] query_ref_author有几百万条数据！如何产生的？可以减少吗？如何创建索引优化？
- [ ] 待处理的comment前加+，使用while(1)，但每次只取10条数据，这样可以保证下次执行程序时不太可能遇到重复的。
- [ ] update.pl会生成uts_to_update.html，显示所有引文数与引用频次不一致的ut。
- [x] 全记录的字段：PMID USAGEIND AUTHORSIDENTIFIERS ACCESSION_NUM FUNDING SUBJECT_CATEGORY JCR_CATEGORY LANG IDS PAGEC SABBR CITREFC ISSN PUBINFO KEYWORDS CITTIMES ADDRS CONFERENCE_SPONSORS DOCTYPE ABSTRACT CONFERENCE_INFO SOURCE TITLE AUTHORS 
- [ ] ut-edition对应关系保存在indexes表，其中键id=(ut,edition)保证唯一性。同理reference2。

## CSCD

- [ ] 把devel上的cscd代码移植过来
- [ ] 上传文件自动检测编码

