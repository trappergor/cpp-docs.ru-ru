---
title: "QueryInterface | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ce14ebef3649cea78e8cf4315a62392cfa142152
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="queryinterface"></a>QueryInterface
Несмотря на то, что существуют механизмы, с помощью которых объект можно выразить функциональные возможности, он предоставляет статически (до создания его экземпляра), основной механизм COM является использование **IUnknown** метод с именем [QueryInterface ](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Каждый интерфейс является производным от **IUnknown**, поэтому каждый интерфейс содержит реализацию `QueryInterface`. Независимо от реализации этот метод отправляет запрос с помощью IID интерфейса, к которому вызывающий указатель объекта. Если объект поддерживает этот интерфейс `QueryInterface` извлекает указатель на интерфейс, при вызове также `AddRef`. В противном случае он возвращает **E_NOINTERFACE** код ошибки.  
  
 Обратите внимание, что должен подчиняться [подсчет ссылок](../atl/reference-counting.md) правила в любое время. При вызове метода **выпуска** на указатель интерфейса, для уменьшения числа ссылок в ноль, не следует использовать этот указатель еще раз. Иногда может потребоваться получить слабую ссылку на объект (то есть, вы можете получить указатель на один из интерфейсов без приращения счетчика ссылок), но не является приемлемым для этого нужно вызвать `QueryInterface` следуют  **Выпуск**. Указатель, полученный таким образом, является недопустимым и не должны использоваться. Это более легко становится очевидной при [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) определен, поэтому определение этого макроса — удобный способ подсчета ошибок поиск ссылок.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [QueryInterface: Навигация в объект](http://msdn.microsoft.com/library/windows/desktop/ms687230)

