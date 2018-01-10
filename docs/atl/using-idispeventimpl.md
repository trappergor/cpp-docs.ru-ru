---
title: "С помощью IDispEventImpl (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDispEventImpl
dev_langs: C++
helpviewer_keywords: IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f787fac05e95fff8a974692c3e6fca24561ed222
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-idispeventimpl"></a>С помощью IDispEventImpl
При использовании `IDispEventImpl` для обработки событий, необходимо:  
  
-   Создайте производный класс от [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
-   Добавьте картой приемника событий в класс.  
  
-   Добавить записи в карте приемник событий, используя [SINK_ENTRY](reference/composite-control-macros.md#sink_entry) или [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex) макрос.  
  
-   Реализуйте методы, что вы заинтересованы в обработке.  
  
-   Сообщить и разъединения источника события.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано, как обрабатывать **DocumentChange** события, создаваемые в Word **приложения** объекта. Это событие определяется как метод на **ApplicationEvents** disp-интерфейса.  
  
 Приведенный пример взят из [ATLEventHandling пример](../visual-cpp-samples.md).  
  
 `[`  
  
 `uuid(000209F7-0000-0000-C000-000000000046),`  
  
 `hidden`  
  
 `]`  
  
 `dispinterface ApplicationEvents {`  
  
 `properties:`  
  
 `methods:`  
  
 `[id(0x00000001), restricted, hidden]`  
  
 `void Startup();`  
  
 `[id(0x00000002)]`  
  
 `void Quit();`  
  
 `[id(0x00000003)]`  
  
 `void DocumentChange();`  
  
 `};`  
  
 В этом примере `#import` для создания файлов обязательный заголовок из библиотеки типов в Word. Если вы хотите использовать этот пример с другими версиями Microsoft Word, необходимо указать правильный mso dll-файла. Например Office 2000 предоставляет mso9.dll и OfficeXP предоставляет mso.dll. Этот код был упрощен из stdafx.h:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#1](../atl/codesnippet/cpp/using-idispeventimpl_1.h)]  
  
 Следующий код отображается в NotSoSimple.h. Комментарии в указывается соответствующий код:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#2](../atl/codesnippet/cpp/using-idispeventimpl_2.h)]  
  
## <a name="see-also"></a>См. также  
 [Обработка событий](../atl/event-handling-and-atl.md)   
 [Образец ATLEventHandling](../visual-cpp-samples.md)

