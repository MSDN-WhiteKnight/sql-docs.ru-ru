---
title: Параметры пользователя и рабочей области
description: Узнайте, как использовать параметры для настройки редактора Azure Data Studio, пользовательского интерфейса и функционального поведения в соответствии с вашими предпочтениями.
ms.prod: azure-data-studio
ms.technology: azure-data-studio
ms.topic: how-to
author: yualan
ms.author: alayu
ms.reviewer: maghan, sstein
ms.custom: seodec18
ms.date: 09/24/2018
ms.openlocfilehash: 06e9efa72ef82d8335db4b7ec6b8941c95501790
ms.sourcegitcommit: 63aef5a96905f0b026322abc9ccb862ee497eebe
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "91364185"
---
# <a name="modify-user-and-workspace-settings"></a>Изменение параметров пользователя и рабочей области

Azure Data Studio можно легко настроить с помощью параметров. Практически все части редактора, пользовательского интерфейса и функционального поведения Azure Data Studio имеют параметры, которые можно изменить.

Azure Data Studio предоставляет две различные области для параметров.

* **Пользователь**. Эти параметры применяются глобально к любому открытому вами экземпляру Azure Data Studio.
* **Рабочая область**. Параметры рабочей области — это параметры, относящиеся к папке на компьютере; они доступны только в том случае, если папка открыта на боковой панели обозревателя. Параметры, определенные в этой области, имеют приоритет над параметрами пользователя.

## <a name="creating-user-and-workspace-settings"></a>Создание параметров пользователя и рабочей области

Команда меню **Файл** > **Настройки** > **Параметры** (**Код** > **Настройки** > **Параметры** на Mac) — точка входа для настройки параметров пользователя и рабочей области. Вам предоставляется список параметров по умолчанию. Скопируйте все параметры, которые необходимо изменить, в соответствующий файл `settings.json`. Вкладки справа позволяют быстро переключаться между файлами параметров пользователя и рабочей области.

Вы также можете открыть параметры пользователя и рабочей области из **палитры команд** (**CTRL+SHIFT+P**) в разделе **Настройки: открыть параметры пользователя** и **Настройки: открыть параметры рабочей области** или используя сочетание клавиш (**CTRL+,** ).

В следующем примере выполняется отключение номеров строк в редакторе и настройка автоматического отступа строк кода.

![Примеры параметров](media/settings/sample-settings.png)

Изменения параметров перезагружаются в Azure Data Studio после сохранения измененного файла `settings.json`.

> [!NOTE]
> Параметры рабочей области полезны для совместного использования параметров конкретного проекта в группе.

## <a name="settings-file-locations"></a>Расположение файлов параметров

В зависимости от платформы файл параметров пользователя находится здесь:

* **Windows** `%APPDATA%\azuredatastudio\User\settings.json`
* **Mac** `$HOME/Library/Application Support/azuredatastudio/User/settings.json`
* **Linux** `$HOME/.config/azuredatastudio/User/settings.json`

Файл параметров рабочей области находится в папке `.Azure Data Studio` проекта.

## <a name="hot-exit"></a>Горячий выход

При завершении работы по умолчанию Azure Data Studio запоминает несохраненные изменения в файлах. Это то же самое, что и функция горячего выхода в Visual Studio Code.

По умолчанию горячий выход отключен. Включите горячий выход, изменив параметр `files.hotExit`. Дополнительные сведения см. в разделе [Горячий выход (в документации Visual Studio Code)](https://code.visualstudio.com/docs/editor/codebasics#_hot-exit).

## <a name="tab-color"></a>Цвет вкладок

Чтобы упростить определение того, с какими подключениями вы работаете, открытым вкладкам в редакторе могут присваиваться цвета, совпадающие с цветом группы серверов, к которой принадлежит соединение. По умолчанию цвета вкладок отключены по умолчанию. Включите цвета вкладок, изменив параметр `sql.tabColorMode`.

## <a name="additional-resources"></a>Дополнительные ресурсы

Так как Azure Data Studio наследует функциональные возможности параметров пользователя и рабочей области из Visual Studio Code, подробные сведения о параметрах см. в статье [Параметры Visual Studio Code](https://code.visualstudio.com/docs/getstarted/settings).
