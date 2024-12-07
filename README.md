# Qt-6.7.3-MariaDB-Driver

[![Qt Version](https://img.shields.io/badge/Qt-6.7.3-green.svg)](https://www.qt.io) 
[![MariaDB Compatible](https://img.shields.io/badge/MariaDB-Compatible-blue.svg)](https://mariadb.org)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)  
[![Stars](https://img.shields.io/github/stars/mwx280/Qt-6.7.3-MariaDB-Drive.svg)](https://github.com/mwx280/Qt-6.7.3-MariaDB-Drive/stargazers) 
[![Forks](https://img.shields.io/github/forks/mwx280/Qt-6.7.3-MariaDB-Drive.svg)](https://github.com/mwx280/Qt-6.7.3-MariaDB-Drive/network/members) 
[![Issues](https://img.shields.io/github/issues/mwx280/Qt-6.7.3-MariaDB-Drive.svg)](https://github.com/mwx280/Qt-6.7.3-MariaDB-Drive/issues)

这是一个为 **Qt 6.7.3** 提供的 **MariaDB(MySQL)** 数据库驱动，已经编译好，护肝。

---

## ✨ 特性
- 适用于 Qt 6.7.3 版本。
- 兼容 MariaDB 和 MySQL。

---

## ⚙️ 环境要求
- **Qt**: 6.7.3
- **MariaDB**:10.11.8（可以自行替换为MySQL或者其他版本）

---

## 📥 安装指南

### 1. 克隆仓库
```bash
git clone https://github.com/mwx280/Qt-6.7.3-MariaDB-Drive.git
```
### 2. 拷贝驱动文件到 Qt 安装目录
- MinGW : 拷贝项目中的 MinGW 驱动到你的 Qt 安装目录 **Qt\6.7.3\mingw_64\plugins\sqldrivers**
- MSVC : 拷贝项目中的 MSVC 驱动到你的 Qt 安装目录 **Qt\6.7.3\msvc2022_64\plugins\sqldrivers**
- MariaDB Drive :拷贝其中的libmariadb库到 **Qt\6.7.3\mingw_64（msvc2022_64）\bin**

## 🛠️ 使用说明
- 在 Qt 应用中使用 MariaDB 驱动：
```bash
#include <QtSql/QSqlDatabase>
#include <QtSql/QSqlQuery>
#include <QtDebug>

int main()
{
    QSqlDatabase db = QSqlDatabase::addDatabase("QMYSQL");
    db.setHostName("localhost");
    db.setDatabaseName("test");
    db.setUserName("root");
    db.setPassword("password");

    if (!db.open())
    {
        qDebug() << "Error:" << db.lastError().text();
        return -1;
    }

    return 0;
}
```

## 📋 注意事项
- 确保 plugins/sqldrivers/ 路径正确无误。
- 使用前可通过以下代码检查驱动是否正确加载：
```
qDebug() << QSqlDatabase::drivers();
```

## 🤝 贡献
- 如果有改进建议或遇到问题，请通过以下方式参与：
  1. 提交 [Issue](https://github.com/mwx280/Qt-6.7.3-MariaDB-Drive/issues)
  2. 提交 [Pull Request](https://github.com/mwx280/Qt-6.7.3-MariaDB-Drive/pulls)
