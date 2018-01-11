---
title: "Распространение клиентских веб-приложений | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Web applications [C++], redistributing
- deploying applications [C++], Web applications
- Internet applications [C++], redistributing
- application deployment [C++], Web applications
ms.assetid: fe05988b-dee8-4a46-b381-016b5103a6bf
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e764e42cb558d2e13e0609cb139e9538a72d09ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="redistributing-web-client-applications"></a>Распространение клиентских веб-приложений
Если приложение использует классы MFC, реализуя элемент управления WebBrowser (например, `CHtmlView` или `CHtmlEditView`), Microsoft Internet Explorer 4.0 или более поздней версии необходимо по крайней мере минимальный установить на целевом компьютере.  
  
 Установка последней версии Internet Explorer также гарантирует, что целевой компьютер имеет последних файлов общих элементов управления.  
  
 Сведения об установке минимальных компонентов Internet Explorer можно найти в следующей статье базы знаний:  
  
-   Q185375, Практическое руководство: Создание одного исполняемого файла установки обозревателя Internet Explorer ([http://support.microsoft.com/support/kb/articles/q185/3/75.asp](http://support.microsoft.com/support/kb/articles/q185/3/75.asp))  
  
 Статьи базы знаний можно найти в библиотеке MSDN или на [http://support.microsoft.com](http://support.microsoft.com).  
  
## <a name="see-also"></a>См. также  
 [Развертывание приложений для настольных систем](../ide/deploying-native-desktop-applications-visual-cpp.md)