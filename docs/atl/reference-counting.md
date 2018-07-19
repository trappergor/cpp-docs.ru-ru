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
ms.openlocfilehash: 8e0ce8b2cc412c576b0eded9662d8e70b34cf2ec
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850817"
---
# <a name="reference-counting"></a>Подсчет ссылок
COM, сам не пытается автоматически удалить объект из памяти, когда он считает, что объект больше не используется. Вместо этого программист объекта необходимо удалить неиспользуемый объект. Программист определяет объект могут ли быть удалены зависимости от счетчика ссылок.  
  
 COM использует `IUnknown` методы, [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317), чтобы управлять количество ссылок на интерфейсы объекта. Ниже приведены общие правила для вызова этих методов.  
  
-   Каждый раз, когда клиент получает указатель интерфейса `AddRef` должен вызываться в интерфейсе.  
  
-   Каждый раз, когда клиент закончит указатель интерфейса, он должен вызвать `Release`.  
  
 В простой реализации каждого `AddRef` вызова увеличивается и каждый `Release` вызовите уменьшает переменную счетчика внутри объекта. Когда счетчик возвращается ноль, интерфейс больше не содержит всех пользователей и может удалить себя из памяти.  
  
 Подсчет ссылок может также быть реализован, чтобы учет каждая ссылка на объект (не для отдельного интерфейса). В этом случае каждый `AddRef` и `Release` вызов делегатов для реализации центра объекта, и `Release` освобождает весь объект, если число ссылок достигает нуля.  
  
> [!NOTE]
>  Когда `CComObject`-производного объекта создается с помощью **новый** оператор, количество ссылок равно 0. Таким образом, вызов `AddRef` должны выполняться после успешного создания `CComObject`-объект, производный от.  
  
## <a name="see-also"></a>См. также  
 [Введение в модель COM](../atl/introduction-to-com.md)   
 [Управление временем существования объектов посредством подсчета ссылок](http://msdn.microsoft.com/library/windows/desktop/ms687260)

