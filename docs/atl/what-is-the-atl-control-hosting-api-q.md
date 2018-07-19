---
title: Что такое ATL размещения элементов управления API? | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- APIs [C++], hosting
- control-hosting API
- controls [ATL], hosting APIs
ms.assetid: 75b27e45-cfba-4950-aa35-96cc7d8da753
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cc85c7ca47d5d1226ffc3089e01c0755ef6c6ac
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850558"
---
# <a name="what-is-the-atl-control-hosting-api"></a>Что такое ATL размещения элементов управления API?
ATL, размещение элементов управления API — это набор функций, позволяющий любое окно в качестве контейнера элементов управления ActiveX. Эти функции могут быть статически или динамически связанной в проект, так как они были доступны в виде исходного кода и предоставляемые ATL90.dll. Функции размещения элементов управления, перечислены в следующей таблице.  
  
|Функция|Описание:|  
|--------------|-----------------|  
|[AtlAxAttachControl](reference/composite-control-global-functions.md#atlaxattachcontrol)|Создает объект главного приложения, подключает его к предоставленным окна, а затем присоединяет существующего элемента управления.|  
|[AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)|Создает объект главного приложения, подключает его к предоставленным окна, а затем загружает в элемент управления.|  
|[AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает его в указанном окне, аналогичную [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol).|  
|[AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)|Создает объект главного приложения, подключает его к предоставленным окна, а затем загружает в элемент управления (также позволяет настроить приемники событий).|  
|[AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrollicex)|Создает лицензированный элемент управления ActiveX, инициализирует его и размещает его в указанном окне, аналогичную [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic).|  
|[AtlAxCreateDialog](reference/composite-control-global-functions.md#atlaxcreatedialog)|Создает немодальное диалоговое окно из ресурса диалогового окна и возвращает дескриптор окна.|  
|[AtlAxDialogBox](reference/composite-control-global-functions.md#atlaxdialogbox)|Создает модальное диалоговое окно из ресурса диалогового окна.|  
|[AtlAxGetControl](reference/composite-control-global-functions.md#atlaxgetcontrol)|Возвращает `IUnknown` указатель интерфейса элемента управления, размещенного в окне.|  
|[AtlAxGetHost](reference/composite-control-global-functions.md#atlaxgethost)|Возвращает `IUnknown` указатель на интерфейс объекта узла подключен к окну.|  
|[AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit)|Инициализирует код размещения элементов управления.|  
|[AtlAxWinTerm](reference/composite-control-global-functions.md#atlaxwinterm)|Отменяет инициализацию кода размещения элементов управления.|  
  
 `HWND` Параметры в первых трех функций должны быть существующее окно (почти) любого типа. При вызове любого из этих трех функций явно (как правило, не придется), не передается дескриптор окна, уже выступает в качестве узла (если в таком случае существующий объект узла не будет освобожден).  
  
 Первые семь функции вызывают [AtlAxWinInit](reference/composite-control-global-functions.md#atlaxwininit) неявно.  
  
> [!NOTE]
>  API размещения элементов управления является основой поддержки ATL в контейнеры элементов управления ActiveX. Тем не менее обычно есть практически не требуется, чтобы вызывать эти функции напрямую в том случае, если воспользоваться преимуществами или наиболее эффективно использовать классы-оболочки ATL. Дополнительные сведения см. в разделе [которого классы упрощают ActiveX вложении элементов управления ATL](which-atl-classes-facilitate-activex-control-containment-q.md).  
  
## <a name="see-also"></a>См. также  
 [Часто задаваемые вопросы о вложении элементов управления](which-atl-classes-facilitate-activex-control-containment-q.md)
