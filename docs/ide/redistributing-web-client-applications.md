---
title: Распространение клиентских веб-приложений | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cdde0f8d4edc13e8c1e1a53d8f4393dc7c2dac40
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372474"
---
# <a name="redistributing-web-client-applications"></a>Распространение клиентских веб-приложений

Если приложение использует классы MFC, реализуя элемент управления WebBrowser (например, `CHtmlView` или `CHtmlEditView`), на целевом компьютере нужно установить Microsoft Internet Explorer 4.0 или более поздней версии.

Установка последней версии Internet Explorer также гарантирует, что целевой компьютер располагает новейшими файлами общих элементов управления.

Сведения об установке минимальных компонентов Internet Explorer можно найти в следующей статье базы знаний:

- Q185375. Практическое руководство: создание установки Internet Explorer из одного исполняемого файла ([http://support.microsoft.com/support/kb/articles/q185/3/75.asp](http://support.microsoft.com/support/kb/articles/q185/3/75.asp))

Статьи базы знаний можно найти в библиотеке MSDN или по адресу [http://support.microsoft.com](http://support.microsoft.com).

## <a name="see-also"></a>См. также

[Развертывание классических приложений](../ide/deploying-native-desktop-applications-visual-cpp.md)