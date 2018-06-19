---
title: Создание всплывающей подсказки для кнопки панели инструментов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 41c2fa538a7888a2f14ae34fde9133b2872d13ba
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33871771"
---
# <a name="creating-a-tool-tip-for-a-toolbar-button"></a>Создание всплывающей подсказки для кнопки панели инструментов
### <a name="to-create-a-tool-tip"></a>Создание всплывающей подсказки  
  
1.  Выберите кнопку панели инструментов.  
  
2.  В [окно свойств](/visualstudio/ide/reference/properties-window)в **Prompt** поле свойства, добавьте описание кнопки для строки состояния, после сообщения, добавьте \n и имя всплывающей подсказки.  
  
 Распространенным примером всплывающей подсказки является кнопкой печати в WordPad:  
  
 1. Открыть программу WordPad.  
  
 2. Наведите указатель мыши на **печати** кнопки панели инструментов.  
  
 3. Обратите внимание, что слово «печать» теперь располагается под указателем мыши.  
  
 4. Выполнить в строке состояния (в самом низу окна WordPad) — Обратите внимание, что она теперь содержит текст «Печать активного документа».  
  
 «Имя всплывающей подсказки» — «Печать» в шаге 3, а «Печать активного документа» из шага 4 — «описание кнопки для строки состояния.»  
  
 Если этот эффект с помощью **инструментов** редакторе задайте **Prompt** свойства **Печать активного документа\nПечать**.  
  
> [!NOTE]
>  Можно изменить с помощью текст приглашения [окно свойств](/visualstudio/ide/reference/properties-window).  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
 Требования  
  
 MFC или ATL  
  
## <a name="see-also"></a>См. также  
 [Создание, перемещение и редактирование кнопок панели инструментов](../windows/creating-moving-and-editing-toolbar-buttons.md)   
 [Редактор панелей инструментов](../windows/toolbar-editor.md)

