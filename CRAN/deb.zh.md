## Debian/Ubuntu 下添加 CRAN 镜像安装 R

参考如下链接中 README 里的步骤

<tmpl>
# Debian 帮助
{{endpoint}}/bin/linux/debian/
# Ubuntu 帮助
{{endpoint}}/bin/linux/ubuntu/fullREADME.html
</tmpl>

编辑 `/etc/apt/sources.list.d/r-mirror.list`

<tmpl z-path="/etc/apt/sources.list.d/r-mirror.list" z-input="release version">
deb {{endpoint}}/bin/linux/{{os}} {{release}}-{{version}}/
</tmpl>

然后运行

<tmpl z-lang="bash">
# Debian 用户添加该公钥
{{sudo}}apt-key adv --keyserver keyserver.ubuntu.com --recv-key '95C0FAF38DB3CCAD0C080A7BDC78B2DDEABC47B7'
# Ubuntu 用户添加该公钥
{{sudo}}apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
{{sudo}}apt-get update
{{sudo}}apt-get install r-base-dev
</tmpl>