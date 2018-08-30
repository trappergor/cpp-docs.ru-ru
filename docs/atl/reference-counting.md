---
title: Справочник по инвентаризации (ATL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1469bef0ef41c72e2ff5e59017088cd63f0f9c79
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194602"
---
# <a name="reference-counting"></a>Подсчет ссылок
COM, сам не пытается автоматически удалить объект из памяти, когда он считает, что объект больше не используется. Вместо этого программист объекта необходимо удалить неиспользуемый объект. Программист определяет объект могут ли быть удалены зависимости от счетчика ссылок.  
  
 COM использует `IUnknown` методы, [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release), чтобы управлять количество ссылок на интерфейсы объекта. Ниже приведены общие правила для вызова этих методов.  
  
-   Каждый раз, когда клиент получает указатель интерфейса `AddRef` должен вызываться в интерфейсе.  
  
-   Каждый раз, когда клиент закончит указатель интерфейса, он должен вызвать `Release`.  
  
 В простой реализации каждого `AddRef` вызова увеличивается и каждый `Release` вызовите уменьшает переменную счетчика внутри объекта. Когда счетчик возвращается ноль, интерфейс больше не содержит всех пользователей и может удалить себя из памяти.  
  
 Подсчет ссылок может также быть реализован, чтобы учет каждая ссылка на объект (не для отдельного интерфейса). В этом случае каждый `AddRef` и `Release` вызов делегатов для реализации центра объекта, и `Release` освобождает весь объект, если число ссылок достигает нуля.  
  
> [!NOTE]
>  Когда `CComObject`-производного объекта создается с помощью **новый** оператор, количество ссылок равно 0. Таким образом, вызов `AddRef` должны выполняться после успешного создания `CComObject`-объект, производный от.  
  
## <a name="see-also"></a>См. также  
 [Введение в модель COM](../atl/introduction-to-com.md)   
 [Управление временем существования объектов посредством подсчета ссылок](/windows/desktop/com/managing-object-lifetimes-through-reference-counting)

