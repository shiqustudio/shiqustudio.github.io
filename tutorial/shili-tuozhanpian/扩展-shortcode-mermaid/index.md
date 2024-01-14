# 扩展 Shortcode - mermaid


[![FixIt 0.2.15 | 更改](https://fixit.lruihao.cn/svg/version/0.2.15-changed.zh-cn.min.svg)](https://github.com/hugo-fixit/FixIt/releases/tag/v0.2.15)

`mermaid` shortcode 使用 [Mermaid](https://mermaidjs.github.io/) 库提供绘制图表和流程图的功能。

[mermaid](https://mermaidjs.github.io/) 是一个可以帮助你在文章中绘制图表和流程图的库，类似 Markdown 的语法。

只需将你的 mermaid 代码插入 `mermaid` shortcode 中即可。

{{&lt; admonition tip&gt;}}

你可以在 `config.toml` 中通过 `params.mermaid` 参数全局配置 mermaid 的主题

{{&lt; /admonition &gt;}}

## 流程图

一个 **流程图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
graph LR;
    A[Hard edge] --&gt;|Link text| B(Round edge)
    B --&gt; C{Decision}
    C --&gt;|One| D[Result one]
    C --&gt;|Two| E[Result two]
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
graph LR;
    A[Hard edge] --&gt;|Link text| B(Round edge)
    B --&gt; C{Decision}
    C --&gt;|One| D[Result one]
    C --&gt;|Two| E[Result two]
{{&lt; /mermaid &gt;}}

## 时序图

一个 **时序图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
sequenceDiagram
    participant Alice
    participant Bob
    Alice-&gt;&gt;John: Hello John, how are you?
    loop Healthcheck
        John-&gt;John: Fight against hypochondria
    end
    Note right of John: Rational thoughts &lt;br/&gt;prevail...
    John--&gt;Alice: Great!
    John-&gt;Bob: How about you?
    Bob--&gt;John: Jolly good!
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
sequenceDiagram
    participant Alice
    participant Bob
    Alice-&gt;&gt;John: Hello John, how are you?
    loop Healthcheck
        John-&gt;John: Fight against hypochondria
    end
    Note right of John: Rational thoughts &lt;br/&gt;prevail...
    John--&gt;Alice: Great!
    John-&gt;Bob: How about you?
    Bob--&gt;John: Jolly good!
{{&lt; /mermaid &gt;}}

## 甘特图

一个 **甘特图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
gantt
dateFormat  YYYY-MM-DD
title Adding GANTT diagram to mermaid
excludes weekdays 2014-01-10

section A section
Completed task            :done,    des1, 2014-01-06,2014-01-08
Active task               :active,  des2, 2014-01-09, 3d
Future task               :         des3, after des2, 5d
Future task2              :         des4, after des3, 5d
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
gantt
dateFormat  YYYY-MM-DD
title Adding GANTT diagram to mermaid
excludes weekdays 2014-01-10

section A section
Completed task            :done,    des1, 2014-01-06,2014-01-08
Active task               :active,  des2, 2014-01-09, 3d
Future task               :         des3, after des2, 5d
Future task2              :         des4, after des3, 5d
{{&lt; /mermaid &gt;}}

## 类图

一个 **类图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
classDiagram
    Animal &lt;|-- Duck
    Animal &lt;|-- Fish
    Animal &lt;|-- Zebra
    Animal : &#43;int age
    Animal : &#43;String gender
    Animal: &#43;isMammal()
    Animal: &#43;mate()
    class Duck{
        &#43;String beakColor
        &#43;swim()
        &#43;quack()
    }
    class Fish{
        -int sizeInFeet
        -canEat()
    }
    class Zebra{
        &#43;bool is_wild
        &#43;run()
    }
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
classDiagram
    Animal &lt;|-- Duck
    Animal &lt;|-- Fish
    Animal &lt;|-- Zebra
    Animal : &#43;int age
    Animal : &#43;String gender
    Animal: &#43;isMammal()
    Animal: &#43;mate()
    class Duck{
        &#43;String beakColor
        &#43;swim()
        &#43;quack()
    }
    class Fish{
        -int sizeInFeet
        -canEat()
    }
    class Zebra{
        &#43;bool is_wild
        &#43;run()
    }
{{&lt; /mermaid &gt;}}

## 状态图

一个 **状态图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
stateDiagram-v2
    [*] --&gt; Still
    Still --&gt; [*]
    Still --&gt; Moving
    Moving --&gt; Still
    Moving --&gt; Crash
    Crash --&gt; [*]
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
stateDiagram-v2
    [*] --&gt; Still
    Still --&gt; [*]
    Still --&gt; Moving
    Moving --&gt; Still
    Moving --&gt; Crash
    Crash --&gt; [*]
{{&lt; /mermaid &gt;}}

## Git 图

一个 **Git 图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
gitGraph
    commit
    commit
    branch develop
    checkout develop
    commit
    commit
    checkout main
    merge develop
    commit
    commit
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
gitGraph
    commit
    commit
    branch develop
    checkout develop
    commit
    commit
    checkout main
    merge develop
    commit
    commit
{{&lt; /mermaid &gt;}}

## 实体关系图

一个 **实体关系图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
{{&lt;/* /mermaid */&gt;}}
```

{{&lt; mermaid &gt;}}
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
{{&lt; /mermaid &gt;}}

## 用户体验旅程图

一个 **用户体验旅程图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
{{&lt; /mermaid &gt;}}

## 饼图

一个 **饼图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
pie
    &#34;Dogs&#34; : 386
    &#34;Cats&#34; : 85
    &#34;Rats&#34; : 15
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
pie
    &#34;Dogs&#34; : 386
    &#34;Cats&#34; : 85
    &#34;Rats&#34; : 15
{{&lt; /mermaid &gt;}}

## 依赖图

一个 **依赖图** `mermaid` 示例:

```markdown
{{&lt;/* mermaid */&gt;}}
requirementDiagram

requirement test_req {
id: 1
text: the test text.
risk: high
verifymethod: test
}

element test_entity {
type: simulation
}

test_entity - satisfies -&gt; test_req
{{&lt;/* /mermaid */&gt;}}
```

呈现的输出效果如下:

{{&lt; mermaid &gt;}}
requirementDiagram

requirement test_req {
id: 1
text: the test text.
risk: high
verifymethod: test
}

element test_entity {
type: simulation
}

test_entity - satisfies -&gt; test_req
{{&lt; /mermaid &gt;}}


---

> 作者:   
> URL: https://blog.funvip.live/tutorial/shili-tuozhanpian/%E6%89%A9%E5%B1%95-shortcode-mermaid/  
> 转载 URL: https://fixit.lruihao.cn/zh-cn/documentation/content-management/shortcodes/extended/mermaid/
