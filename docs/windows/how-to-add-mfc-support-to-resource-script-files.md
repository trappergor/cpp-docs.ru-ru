---
title: 'Как: Добавление поддержки MFC в файлы описания ресурсов | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.add.MFC
dev_langs:
- C++
helpviewer_keywords:
- rc files, adding MFC support
- .rc files, adding MFC support
- MFC, adding support to resource scripts files
- resource script files, adding MFC support
ms.assetid: 599dfe9d-ad26-4e34-899c-49b56599e37f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50c0493e630c2b141da1fced6964ffc514c761d4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-add-mfc-support-to-resource-script-files"></a>Практическое руководство. Добавление поддержки MFC в файлы описания ресурсов
Как правило, при построении приложения MFC для Windows с помощью [мастер приложений MFC](../mfc/reference/mfc-application-wizard.md), мастер создает базовый набор файлов (включая RC-файла ресурсов), который содержит основные функции Microsoft Foundation классы (MFC). Однако при редактировании RC-файла для приложения Windows, в основе которого не лежит MFC, будут недоступны следующие возможности, предназначенные для платформы MFC.  
  
-   Мастеры кода MFC (предыдущее название «[мастер классов MFC](http://msdn.microsoft.com/en-us/98dc2434-ba93-4e0b-b084-1a4bc26cdf1e)»)  
  
-   Строки подсказок для меню.  
  
-   Содержимое списков для элементов управления "поле со списком".  
  
-   Размещение элементов управления ActiveX.  
  
 Тем не менее можно добавить поддержку MFC для существующих RC-файлов, которые ее не имеют.  
  
### <a name="to-add-mfc-support-to-rc-files"></a>Добавление поддержки MFC в RC-файлы  
  
1.  Откройте файл описания ресурсов.  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В [представление ресурсов](../windows/resource-view-window.md), выделите папку ресурсов (например, MFC.rc).  
  
3.  В [окно свойств](/visualstudio/ide/reference/properties-window), задайте **режим MFC** свойства **True**.  
  
    > [!NOTE]
    >  Кроме того, что будет установлен этот флаг, RC-файл должен быть частью проекта MFC. Например, если просто задать **режим MFC** для **True** RC-файл в Win32 проекта вы не получите действующие функции MFC.  
  

  
 **Требования**  
  
 MFC  
  
## <a name="see-also"></a>См. также  
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)