---
title: "Справочник по инвентаризации (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- AddRef method [C++], reference counting
- reference counting
- AddRef method [C++]
- reference counts
- references, counting
ms.assetid: b1fd4514-6de6-429f-9e60-2777c0d07a3d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be6aff46df500a55665f85f6f462514985885b9b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="reference-counting"></a>Подсчет ссылок
COM, сам не пытается автоматически удалить объект из памяти, когда он полагает, что объект больше не используется. Вместо этого программист объекта необходимо удалить неиспользуемый объект. Программист определяет ли объект может быть удален в соответствии с счетчик ссылок.  
  
 COM используется **IUnknown** методы, [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) и [выпуска](http://msdn.microsoft.com/library/windows/desktop/ms682317), для управления подсчетом ссылок из интерфейсов объекта. Ниже приведены общие правила для вызова этих методов.  
  
-   Каждый раз, когда клиент получает указатель интерфейса `AddRef` должен вызываться в интерфейсе.  
  
-   Каждый раз, когда клиент завершения с помощью указателя интерфейса, необходимо вызвать **выпуска**.  
  
 В простой реализации каждый `AddRef` вызова шагами и каждого **выпуска** вызова уменьшает переменную счетчика внутри объекта. По возвращении счетчик до нуля, интерфейс больше не содержит всех пользователей и может удалить себя из памяти.  
  
 Подсчет ссылок может также быть реализован, чтобы учет каждая ссылка на объект (не для отдельного интерфейса). В этом случае каждый `AddRef` и **выпуска** вызов делегатов в центре реализацию объекта и **выпуска** освобождает объект целиком, если число ссылок достигает нуля.  
  
> [!NOTE]
>  Когда `CComObject`-производного объекта создается с помощью **новый** оператор, количество ссылок равно 0. Таким образом, вызов `AddRef` должны выполняться после успешного создания `CComObject`-производного объекта.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [Управление временем жизни объектов посредством подсчета ссылок](http://msdn.microsoft.com/library/windows/desktop/ms687260)

