---
title: "环境安装"
nav-parent_id: python
nav-pos: 15
---
<!--
Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
-->

* This will be replaced by the TOC
{:toc}

## 环境要求
<span class="label label-info">注意</span> PyFlink需要特定的Python版本（3.5, 3.6, 3.7 或 3.8）。请运行以下命令，以确保Python版本满足要求。

{% highlight bash %}
$ python --version
# the version printed here must be 3.5, 3.6, 3.7 or 3.8
{% endhighlight %}

## 环境设置

你的系统也许安装了好几个版本的Python。你可以运行下面的`ls`命令来查看你系统中安装的Python版本有哪些:

{% highlight bash %}
$ ls /usr/bin/python*
{% endhighlight %}

为了满足Python版本要求，你可以选择通过软链接的方式将`python`指向`python3`解释器:

{% highlight bash %}
ln -s /usr/bin/python3 python
{% endhighlight %}

除了软链接的方式，你也可以选择创建一个Python virtual env（`venv`）的方式。关于如何创建一个virtual env，你可以参考[准备Python虚拟环境]({% link dev/python/faq.zh.md %}#preparing-python-virtual-environment)

如果你不想使用软链接的方式改变系统`python`解释器的指向的话，你可以使用配置的方式指定Python解释器。
关于指定编译作业使用的Python解释器，你可以参考[python client executable]({% link dev/python/python_config.zh.md %}#python-client-executable)
关于指定执行python udf worker使用Python解释器，你可以参考[python executable]({% link dev/python/python_config.zh.md %}#python-executable)

## PyFlink 安装

PyFlink已经被发布到[PyPi](https://pypi.org/project/apache-flink/)，可以通过如下方式安装PyFlink：

{% highlight bash %}
{% if site.is_stable %}
$ python -m pip install apache-flink {{ site.version }}
{% else %}
$ python -m pip install apache-flink
{% endif %}
{% endhighlight %}

您也可以从源码手动构建PyFlink，具体可以参见[开发指南]({% link flinkDev/building.zh.md %}#build-pyflink).

<span class="label label-info">注意</span> 从Flink 1.11版本开始, PyFlink作业支持在Windows系统上运行，因此您也可以在Windows上开发和调试PyFlink作业了。
