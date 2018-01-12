---
title: "Интерфейсы (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bf1dd68a3ca8e6735b07c5bd7247b457bd7d246d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="interfaces-atl"></a>Интерфейсы (ATL)
Интерфейс является способом, в котором объект предоставляет свои функции с внешним миром. В модели COM интерфейс — это таблица указателей (как в таблице vtable C++) для функций, реализованных данным объектом. Таблица представляет интерфейс, и функции, на которые он указывает представляют собой методы этого интерфейса. Объект может предоставлять столько интерфейсы, как он выбирает.  
  
 Каждый интерфейс основан на основной COM-интерфейса [IUnknown](../atl/iunknown.md). Методы **IUnknown** позволяют переходить на другие интерфейсы, предоставляемые объектом.  
  
 Кроме того каждый интерфейс присваивается уникальный идентификатора интерфейса (IID). Эта уникальность упрощает поддерживают управление версиями интерфейса. Новая версия интерфейса, просто новый интерфейс, с новой IID.  
  
> [!NOTE]
>  Стандартные IID для стандартные интерфейсы COM и OLE.  
  
## <a name="see-also"></a>См. также  
 [Знакомство с COM](../atl/introduction-to-com.md)   
 [COM-объекты и интерфейсы](http://msdn.microsoft.com/library/windows/desktop/ms690343)

