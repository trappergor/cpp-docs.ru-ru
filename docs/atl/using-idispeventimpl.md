---
title: С помощью IDispEventImpl (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- IDispEventImpl
dev_langs:
- C++
helpviewer_keywords:
- IDispEventImpl class, using
ms.assetid: 82d53b61-9d0d-45c5-aff9-2fafa468a9ca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 520d1129234a26ff6eb4c402154969ad7e166211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361155"
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

