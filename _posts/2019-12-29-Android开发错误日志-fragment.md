#### Fragment 中嵌套Fragment ，viewpager加载 Fragment 空白页

```
time:2019-12-29
author:朱红喜
```



#### 问题：

`当我们在fragment中使用viewPaper来切换fragment，作为二级的fragment切换时，会出现空白页的现象。`

#### 分析：

```getFragmentManager()是本级别管理者, getChildFragmentManager()是下一级别管理者.
这实际上是一个树形管理结构.
在Fragment里面嵌套Fragment 的话，不要用getActivity().getSupportFragmentManager()或者       getFragmentManager()
会在ViewPager中出现。有些Fragment 不会加载的情况，既ViewPager 加载 Fragment 空白页的情况。
```

#### 解决方法：

   ```Fragment里面嵌套Fragment 的话：一定要用getChildFragmentManager();
 getFragmentManager()是所在fragment 父容器的碎片管理，
 getChildFragmentManager()是在fragment  里面子容器的碎片管理。
 getFragmentManager()是本级别管理者, getChildFragmentManager()是下一级别管理者.
   ```

