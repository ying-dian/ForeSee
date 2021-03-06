# ForeSee_Spiders



## 数据说明

**【数据目录】**

* [股票基本信息](#股票基本信息)
* [公司地理信息](#地理信息)
* [股票公告信息](#股票公告信息)
* [股票新闻信息](#股票新闻信息)
* [行业分析报告](#行业分析报告)

### 股票基本信息

* 路径：/data/prj2020/EnterpriseSpider/basic/BasicInfoFile/

* 组织方式

    * 一个行业对应一个目录
    * 一个目录下包含该行业所有股票的基本信息，每只股票对应一个json

* 字段

    |    字段名     |   字段含义    |
    | :-----------: | :-----------: |
    |    entName    |    公司名     |
    |   authority   |   登记机关    |
    |   district    |   行政区划    |
    |   describe    |     简介      |
    |   district    |   行政区划    |
    |    entType    |   企业类型    |
    |   industry    |   所属行业    |
    |  openStatus   |   经营状态    |
    |  legalPerson  |  法定代表人   |
    |     scope     |   经营范围    |
    |   startDate   |   成立日期    |
    |  regCapital   |   注册资本    |
    |  annualDate   | 审核/年检日期 |
    | licenseNumber |  工商注册号   |
    |   openTime    |   营业期限    |
    |     orgNo     | 组织机构代码  |
    |     regNo     | 纳税人识别号  |
    |    regAddr    |   注册地址    |
    |  prevEntName  |    曾用名     |
    |  realCapital  |   实缴资本    |
    |    entLogo    |   logo地址    |
    | industry_code |   行业代码    |
    |  stock_code   |   股票代码    |

* 示例数据

    ```json
    {
        "entName": "上海吉祥航空股份有限公司",
        "authority": "上海市市场监督管理局",
        "district": "上海市市辖区",
        "describe": "上海吉祥航空股份有限公司成立于2006年03月23日，注册地位于中国（上海）自由贸易试验区康桥东路8号，法定代表人为王均金。经营范围包括国内（含港澳台）航空客货运输业务、国际航空客货运输业务，航空配餐，飞机零配件的制造，日用百货，五金交电，纺织品，电子产品，家用电器，文化用品，工艺美术品，化工原料（除危险品），金属材料，仪器仪表，机械设备，汽车配件的销售，从事货物及技术的进出口业务 【依法须经批准的项目，经相关部门批准后方可开展经营活动】上海吉祥航空股份有限公司对外投资11家公司，具有28处分支机构。",
        "entType": "其他股份有限公司(上市)",
        "industry": "航空运输业",
        "openStatus": "开业",
        "legalPerson": "王均金",
        "scope": "国内（含港澳台）航空客货运输业务、国际航空客货运输业务，航空配餐，飞机零配件的制造，日用百货，五金交电，纺织品，电子产品，家用电器，文化用品，工艺美术品，化工原料（除危险品），金属材料，仪器仪表，机械设备，汽车配件的销售，从事货物及技术的进出口业务 【依法须经批准的项目，经相关部门批准后方可开展经营活动】",
        "startDate": "2006-03-23",
        "regCapital": "196,614.4157万(元)",
        "annualDate": "2020-08-28",
        "licenseNumber": "310225000502571",
        "openTime": "2006-03-23 至 无固定期限",
        "orgNo": "78672261-0",
        "regNo": "913100007867226104",
        "regAddr": "中国（上海）自由贸易试验区康桥东路8号",
        "prevEntName": "-",
        "realCapital": "-",
        "entLogo": "https:\\/\\/zhengxin-pub.cdn.bcebos.com\\/logopic\\/9eea4232d1cd05c09f96833771f88c19_fullsize.jpg",
        "industry_code": "BK0420",
        "stock_code": "603885"
    }
    ```

### 公司地理信息

* 路径：/data/prj2020/EnterpriseSpider/geoInfo/geoData/

* 组织方式：一个行业对应一个json文件

* 字段说明

    |    字段名     | 字段含义 |
    | :-----------: | :------: |
    |      lng      |   经度   |
    |      lat      |   纬度   |
    | company_name  |  公司名  |
    |  stock_code   | 股票代码 |
    | industry_code | 行业代码 |

* 示例数据

    ```jaon
    [
      {
        "lng": 113.53876275227442,
        "lat": 23.17690644097641,
        "company_name": "中国南方航空股份有限公司",
        "stock_code": "600029",
        "industry_code": "BK0420"
      },
      {
        "lng": 121.78117141901282,
        "lat": 31.173326869615515,
        "company_name": "中国东方航空股份有限公司",
        "stock_code": "600115",
        "industry_code": "BK0420"
      }
    ]
    ```

### 股票公告信息

* 路径：/data/prj2020/EnterpriseSpider/notice/data/

* 组织方式

    * 一个行业对应一个目录
    * 一个目录下包含该行业所有股票的公告信息，每只股票对应一个json

* 字段说明

    * 股票部分

        |       字段名        |                字段含义                 |
        | :-----------------: | :-------------------------------------: |
        |    industry_code    |                行业代码                 |
        |     stock_code      |                股票代码                 |
        |    company_name     |                 公司名                  |
        |     stock_name      |                 股票名                  |
        | notice_info \| 数组 | 该股票所有公告 \|  一个公告对应一个字典 |

    * 公告部分，即`notice_info`中每个字典

        |    字段名    |   字段含义   |
        | :----------: | :----------: |
        | notice_title |    公告名    |
        | notice_time  | 公告发布时间 |
        |     link     |   公告链接   |

* 示例数据

    ```json
    {
      "industry_code": "BK0420",
      "stock_code": "600115",
      "company_name": "中国东方航空股份有限公司",
      "stock_name": "东方航空",
      "notice_info": [
        {
          "notice_title": "董事会决议公告",
          "notice_time": "2012-03-25",
          "link": "http://static.cninfo.com.cn/finalpage/2012-03-26/60724323.PDF"
        },
        {
          "notice_title": "监事会决议公告",
          "notice_time": "2012-03-25",
          "link": "http://static.cninfo.com.cn/finalpage/2012-03-26/60724324.PDF"
        }
      ]
    }
    ```

### 股票新闻信息

* 路径：/data/prj2020/EnterpriseSpider/news/news_all.json

* 组织方式

    * 一个json文件包含所有信息
    * 最外层为数组，每个行业为一个字典
    * all_news_info为数组，包含该行业所有股票对应的字典

* 字段说明

    * 行业部分

        |        字段名         |                      字段含义                      |
        | :-------------------: | :------------------------------------------------: |
        |     industry_code     |                      行业代码                      |
        | all_news_info \| 数组 | 该行业下每只股票的新闻信息 \| 一只股票对应一个字典 |

    * 股票部分，即`all_news_info`中每个字典

        |    字段名    |                字段含义                |
        | :----------: | :------------------------------------: |
        |  stock_code  |                股票代码                |
        |  stock_name  |                公司名字                |
        | news \| 数组 | 该股票所有新闻 \| 每个新闻对应一个字典 |

    * 新闻部分，即`news`中每个字典

        |   字段名   |   字段含义   |
        | :--------: | :----------: |
        | news_title |    新闻名    |
        | news_time  | 新闻发布时间 |
        | news_link  |   新闻链接   |

* 示例数据

    ```json
    [
      {
        "industry_code": "BK0537",
        "all_news_info": [
          {
            "stock_code": 300433,
            "stock_name": "蓝思科技股份有限公司",
            "news": [
              {
                "news_title": "A股10月开门红：光伏板块掀涨停潮 四季度将如何演绎？",
                "news_time": "2020-10-09",
                "news_link": "'https://finance.sina.com.cn/roll/2020-10-09/doc-iivhuipp8718778.shtml'"
              },
              {
                "news_title": "5GiPhone来袭:苹果产业链四季度机会确定 5G应用端投资值得期待",
                "news_time": "2020-10-09",
                "news_link": "'https://finance.sina.com.cn/stock/hyyj/2020-10-09/doc-iivhuipp8764425.shtml'"
              }
            ]
          },
          {
            "stock_code": 601012,
            "stock_name": "隆基绿能科技股份有限公司",
            "news": [
              {
                "news_title": "A股10月开门红：光伏板块掀涨停潮 四季度将如何演绎？",
                "news_time": "2020-10-09",
                "news_link": "'https://finance.sina.com.cn/roll/2020-10-09/doc-iivhuipp8718778.shtml'"
              },
              {
                "news_title": "隆基股份获沪股通连续4日净买入 累计净买入12.03亿元",
                "news_time": "2020-10-09",
                "news_link": "'https://finance.sina.com.cn/stock/relnews/cn/2020-10-09/doc-iivhvpwz1144049.shtml'"
              }
            ]
          }
        ]
      },
      {
        "industry_code": "BK0420",
        "all_news_info": [
          
        ]
      }
    ]
    ```

### 行业分析报告

* 路径：/data/prj2020/EnterpriseSpider/analysis/

* 组织方式

    * Internet_article_abstract.json：用于存储每篇行业分析的文章唯一标示符和摘要
    * Internet_article_info.json：用于存储每篇行业分析的基本信息

    > 注意：当前只有一个行业的信息（互联网）

* 字段说明

    * 文章摘要：Internet_article_abstract.json

        |  字段名  |    字段含义    |
        | :------: | :------------: |
        |    id    | 文章唯一标示符 |
        | abstract |    文章摘要    |

    * 文章基本信息：Internet_article_info.json

        |        字段名        |                         字段含义                         |
        | :------------------: | :------------------------------------------------------: |
        |        title         |                         文章标题                         |
        |         link         |                         文章链接                         |
        |         aid          |                      文章唯一标示符                      |
        | pub_date \| 字典类型 | 分三个字段记录<br />year：年<br />month：月<br />day：日 |
        |    analysis_year     |                     文章所分析的年份                     |

* 示例数据

    * 文章摘要

        ```json
        [
          {
            "id": "/industry/202010/899513",
            "abstract": "物联网（Internet of Things）的概念最早由美国麻省理工学院Kevin教授在1991年提出，但是并未引起广泛的关注。直到2000年后，随"
          },
          {
            "id": "/industry/202010/899307",
            "abstract": "云计算（cloudcomputing）是分布式计算的一种，指的是通过网络“云”将巨大的数据计算处理程序分解成无数个小程序，然后，通过多部服务器组成的系"
          }
        ]
        ```

    * 文章基本信息

        ```json
        [
          {
            "title": "2019年中国物联网操作系统市场规模10.92亿元 本土企业占主导地位 行业发展政策及路径分析[图]",
            "link": "http://www.chyxx.com/industry/202010/899513.html",
            "aid": "/industry/202010/899513",
            "pub_date": {
              "year": 2020,
              "month": "10",
              "day": "10"
            },
            "analysis_year": "2019"
          },
          {
            "title": "2020年全球公有云市场规模及行业发展趋势分析[图]",
            "link": "http://www.chyxx.com/industry/202010/899307.html",
            "aid": "/industry/202010/899307",
            "pub_date": {
              "year": 2020,
              "month": "10",
              "day": "9"
            },
            "analysis_year": "2020"
          }
        ]
        ```

        