---
title: QueryInterface | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3227ebd4767bd7639bb5e5d8d5a1c73e26079dc
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953425"
---
# <a name="queryinterface"></a>QueryInterface
Хотя существуют механизмы, по которым объект можно выразить функциональные возможности, он предоставляет статически (до создания его экземпляра), основной механизм COM является использование `IUnknown` метод под названием [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms682521).  
  
 Каждый интерфейс является производным от `IUnknown`, поэтому каждый интерфейс имеет реализацию `QueryInterface`. Независимо от реализации этот метод запрашивает объект, используя идентификатор IID интерфейса, к которому вызывающий указатель. Если объект поддерживает этот интерфейс `QueryInterface` извлекает указатель на интерфейс, при одновременном вызове `AddRef`. В противном случае он возвращает код ошибки E_NOINTERFACE.  
  
 Обратите внимание, что должен подчиняться [подсчет ссылок](../atl/reference-counting.md) правила все время. При вызове метода `Release` на указатель интерфейса, чтобы уменьшить счетчик до нуля, не следует использовать этот указатель еще раз. Иногда необходимо получить слабую ссылку на объект (то есть вы можете получить указатель на один из интерфейсов без приращения счетчика ссылок), но не является допустимым для этого нужно вызвать `QueryInterface` следуют `Release`. Указатель, полученный таким образом, является недопустимым и не должны использоваться. Это более эффективно становится очевидной при [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) определен, поэтому определение этого макроса — это удобный способ подсчета ошибок поиск ссылок.  
  
## <a name="see-also"></a>См. также  
 [Введение в модель COM](../atl/introduction-to-com.md)   
 [QueryInterface: Навигация в объект](http://msdn.microsoft.com/library/windows/desktop/ms687230)

