---
title: "Что такое библиотеки ATL размещение элементов управления API? | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- APIs [C++], hosting
- control-hosting API
- controls [ATL], hosting APIs
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3e985ffd3b514feec81f4fee540a95792eb3658e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="what-is-the-atl-control-hosting-api"></a>Что такое библиотеки ATL размещение элементов управления API?
ATL, размещение элементов управления API — это набор функций, позволяющий любое окно в качестве контейнера элементов управления ActiveX. Эти функции могут быть статически или динамически связан в проект, так как они доступны в виде исходного кода и предоставляемые ATL90.dll. В следующей таблице перечислены функции размещение элементов управления.  
  
|Функция|Описание:|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Создает объект узла, подключает его указанного окна, а затем присоединяет существующий элемент управления.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Создает объект узла, подключает его указанного окна, а затем загружает в элемент управления.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне аналогично [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Создает объект узла, подключает его указанного окна, а затем загружает элемент управления (также позволяет настроить приемники событий).|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает в указанном окне аналогично [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|Создает немодальное диалоговое окно из ресурса диалогового окна и возвращает дескриптор окна.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Создает модальное диалоговое из ресурса диалогового окна.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Возвращает **IUnknown** указатель интерфейса элемента управления, размещенного в окне.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Возвращает **IUnknown** указатель на интерфейс объекта узла подключен к окну.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Инициализирует код размещения элемента управления.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Отменяет инициализацию кода размещения элемента управления.|  
  
 `HWND` Параметры в первые три функции должны быть существующему окну практически любого типа. Если любой из этих трех функций явно вызывать (как правило, не придется), не передается дескриптор окна, уже работает в качестве узла (в противном случае существующий объект узла не будет освобождена).  
  
 Первые семь функции вызывают [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) неявно.  
  
> [!NOTE]
>  API размещения элементов управления форм foundation поддержки ATL контейнеры элементов управления ActiveX. Однако обычно нет необходимости вызывать эти функции напрямую, если наиболее эффективно использовать классы-оболочки ATL или воспользоваться преимуществами. Дополнительные сведения см. в разделе [которого классы упрощают ActiveX вложении элементов управления ATL](which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## <a name="see-also"></a>См. также  
 [Часто задаваемые вопросы о вложении элементов управления](which-atl-classes-facilitate-activex-control-containment-q.md)
