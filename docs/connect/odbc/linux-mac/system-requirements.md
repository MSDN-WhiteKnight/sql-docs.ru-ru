---
title: Требования к системе (драйвер ODBC для SQL Server)
description: Здесь перечислены требования к системе для драйвера ODBC для SQL Server на Linux и macOS.
ms.custom: ''
ms.date: 08/06/2020
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- prerequisites
- system requirements
- requirements
ms.assetid: f03b7fdd-0e9d-4e74-958d-e8c87e027348
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 74b7bf1680dd956dfca85917939ad24a3559d7de
ms.sourcegitcommit: e8f6c51d4702c0046aec1394109bc0503ca182f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2020
ms.locfileid: "87934463"
---
# <a name="system-requirements-linux-and-macos"></a>Требования к системе (Linux и macOS)

[!INCLUDE[Driver_ODBC_Download](../../../includes/driver_odbc_download.md)]

Эта статья содержит требования для использования драйвера [!INCLUDE[msCoName](../../../includes/msconame_md.md)] ODBC Driver 13 for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в Linux и macOS.

## <a name="sql-version-compatibility"></a>Совместимость с версиями SQL

Совместимость с версиями SQL для драйверов Linux и macOS аналогична [совместимости для драйверов Windows](../windows/system-requirements-installation-and-driver-files.md#sql-version-compatibility).

## <a name="operating-system-support"></a>Поддержка операционных систем

Версии 17, 13.1 и 13 драйверов Linux и macOS поддерживаются для архитектур x64 следующих операционных систем:

|Версия драйвера&nbsp;&#8594;<br />&#8595; Операционная система     |17.6|17.5|17.4|17.3|17.2|17.1|17.0|Версия 13.1|13|
|-------------------------------|----|----|----|----|----|----|----|----|---|
|Apple OS X 10.11 (El Capitan)  |    |    |Да |Да |Да |Да |Да |Да |Да|
|Apple macOS 10.12 (Sierra)     |    |    |Да |Да |Да |Да |Да |Да |Да|
|Apple macOS 10.13 (High Sierra)|Да |Да |Да |Да |Да |Да |Да |Да |Да|
|Apple macOS 10.14 (Mojave)     |Да |Да |Да |Да |    |    |    |    |   |
|Apple macOS 10.15 (Catalina)   |Да |Да |    |    |    |    |    |    |   |
|Alpine Linux 3.11              |Да |Да |    |    |    |    |    |    |   |
|Debian Linux 8                 |Да |Да |Да |Да |Да |Да |Да |Да |Да|
|Debian Linux 9                 |Да |Да |Да |Да |Да |Да |Да |Да |Да|
|Debian Linux 10                |Да |Да |Да |    |    |    |    |    |   |
|Oracle Linux 8                 |Да |Да |    |    |    |    |    |    |   |
|RedHat Enterprise Linux 6      |Да |Да |Да |Да |Да |Да |Да |Да |Да|
|RedHat Enterprise Linux 7      |Да |Да |Да |Да |Да |Да |Да |Да |Да|
|RedHat Enterprise Linux 8      |Да |Да |Да |    |    |    |    |    |   |
|SUSE Linux Enterprise Server 11<sup>1</sup>|Да |Да |Да |Да |Да |Да |Да |Да |Да|
|SUSE Linux Enterprise Server 12|Да |Да |Да |Да |Да |Да |Да |Да |Да|
|SUSE Linux Enterprise Server 15|Да |Да |Да |Да |    |    |    |    |   |
|Ubuntu Linux 14.04             |    |    |Да |Да |Да |Да |Да |Да |Да|
|Ubuntu Linux 16.04             |Да |Да |Да |Да |Да |Да |Да |Да |Да|
|Ubuntu Linux 18.04             |Да |Да |Да |Да |Да |    |    |    |   |
|Ubuntu Linux 20.04             |Да |    |    |    |    |    |    |    |   |

<sup>1</sup> Драйвер ODBC версии 17 поддерживает только SUSE Linux Enterprise Server 11 SP4

Пакеты установки для [!INCLUDE[msCoName](../../../includes/msconame_md.md)] ODBC Driver 13, 13.1 и 17 for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] в Linux и macOS разрешают зависимости драйвера автоматически при установке с помощью системы управления пакетами дистрибутива, как описано в разделах [Установка ODBC Driver (Linux)](installing-the-microsoft-odbc-driver-for-sql-server.md) и [Установка ODBC Driver (macOS)](install-microsoft-odbc-driver-sql-server-macos.md).

## <a name="microsoft-odbc-driver-11-for-sql-server"></a>Драйвер Microsoft ODBC 11 для SQL Server  
  
* 64-разрядный диспетчер драйверов UnixODBC 2.3.0, созданный для 64-разрядных SQLLEN/SQLULEN. Более поздние версии 64-разрядного диспетчера драйверов UnixODBC не поддерживаются для драйвера ODBC в Linux. Подробнее см. в разделе [Installing the Driver Manager](../../../connect/odbc/linux-mac/installing-the-driver-manager.md) .  
  
* Драйвер ODBC для **Red Hat Enterprise Linux 5 (64-разрядная версия)** требует наличия следующих пакетов, и его можно скачать здесь: [Microsoft ODBC Driver 11 for SQL Server — Red Hat Linux](https://go.microsoft.com/fwlink/?LinkId=267321)  
  * `glibc`  
  * `libgcc`  
  * `libstdc++`  
  * `e2fsprogs-libs`  
  * `krb5-libs`  
  * `openssl`  
  
* Драйвер ODBC для **Red Hat Enterprise Linux 6 (64-разрядная версия)** требует наличия следующих пакетов, и его можно скачать здесь: [Microsoft ODBC Driver 11 for SQL Server — Red Hat Linux](https://go.microsoft.com/fwlink/?LinkId=267321)  
  * `glibc`  
  * `libgcc`  
  * `libstdc++`  
  * `libuuid`  
  * `krb5-libs`  
  * `openssl`  
  
* Драйвер ODBC для **SUSE Linux Enterprise 11 с пакетом обновления 2 (64-разрядная версия)** требует наличия следующих пакетов, и его можно скачать здесь: [Microsoft ODBC Driver 11 Previews for SQL Server — SUSE Linux](https://go.microsoft.com/fwlink/?LinkId=264916)  
  * `glibc`  
  * `libstdc++46`  
  * `libgcc46`  
  * `libuuid1`  
  * `krb5`  
  * `libopenssl0_9_8`  
  
## <a name="see-also"></a>См. также:

[Установка диспетчера драйверов](../../../connect/odbc/linux-mac/installing-the-driver-manager.md)  
[Известные проблемы в данной версии драйвера](../../../connect/odbc/linux-mac/known-issues-in-this-version-of-the-driver.md)  
[Заметки о выпуске](../../../connect/odbc/linux-mac/release-notes-odbc-sql-server-linux-mac.md)  
