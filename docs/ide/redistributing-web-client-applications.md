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
ms.openlocfilehash: d036f7d46e0db84b8572b26c747947c929972517
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/09/2018
ms.locfileid: "48889936"
---
# <a name="redistributing-web-client-applications"></a>Распространение клиентских веб-приложений

Если приложение использует классы MFC, реализуя элемент управления WebBrowser (например, `CHtmlView` или `CHtmlEditView`), на целевом компьютере нужно установить Microsoft Internet Explorer 4.0 или более поздней версии.

Установка последней версии Internet Explorer также гарантирует, что целевой компьютер располагает новейшими файлами общих элементов управления. Дополнительные сведения см. в статье [Установка и развертывание Internet Explorer 11](/internet-explorer/ie11-deploy-guide/install-and-deploy-ie11).

## <a name="see-also"></a>См. также

[Развертывание классических приложений](../ide/deploying-native-desktop-applications-visual-cpp.md)