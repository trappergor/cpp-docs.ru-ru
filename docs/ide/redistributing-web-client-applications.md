---
title: Распространение клиентских веб-приложений
ms.date: 11/04/2016
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
ms.openlocfilehash: 37ff666493ada7dada19f5731e6581603d3cb57e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512424"
---
# <a name="redistributing-web-client-applications"></a>Распространение клиентских веб-приложений

Если приложение использует классы MFC, реализуя элемент управления WebBrowser (например, `CHtmlView` или `CHtmlEditView`), на целевом компьютере нужно установить Microsoft Internet Explorer 4.0 или более поздней версии.

Установка последней версии Internet Explorer также гарантирует, что целевой компьютер располагает новейшими файлами общих элементов управления. Дополнительные сведения см. в статье [Установка и развертывание Internet Explorer 11](/internet-explorer/ie11-deploy-guide/install-and-deploy-ie11).

## <a name="see-also"></a>См. также

[Развертывание классических приложений](../ide/deploying-native-desktop-applications-visual-cpp.md)