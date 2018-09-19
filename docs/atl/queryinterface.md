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
ms.openlocfilehash: c361bc9510c610f2004af9f09c061d6f4b8b8cd2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46057454"
---
# <a name="queryinterface"></a>QueryInterface

Хотя существуют механизмы, по которым объект можно выразить функциональные возможности, он предоставляет статически (до создания его экземпляра), основной механизм COM является использование `IUnknown` метод под названием [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

Каждый интерфейс является производным от `IUnknown`, поэтому каждый интерфейс имеет реализацию `QueryInterface`. Независимо от реализации этот метод запрашивает объект, используя идентификатор IID интерфейса, к которому вызывающий указатель. Если объект поддерживает этот интерфейс `QueryInterface` извлекает указатель на интерфейс, при одновременном вызове `AddRef`. В противном случае он возвращает код ошибки E_NOINTERFACE.

Обратите внимание, что должен подчиняться [подсчет ссылок](../atl/reference-counting.md) правила все время. При вызове метода `Release` на указатель интерфейса, чтобы уменьшить счетчик до нуля, не следует использовать этот указатель еще раз. Иногда необходимо получить слабую ссылку на объект (то есть вы можете получить указатель на один из интерфейсов без приращения счетчика ссылок), но не является допустимым для этого нужно вызвать `QueryInterface` следуют `Release`. Указатель, полученный таким образом, является недопустимым и не должны использоваться. Это более эффективно становится очевидной при [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) определен, поэтому определение этого макроса — это удобный способ подсчета ошибок поиск ссылок.

## <a name="see-also"></a>См. также

[Введение в модель COM](../atl/introduction-to-com.md)<br/>
[QueryInterface: Навигация в объект](/windows/desktop/com/queryinterface--navigating-in-an-object)

