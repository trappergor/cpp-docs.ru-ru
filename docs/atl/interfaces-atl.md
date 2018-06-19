---
title: Интерфейсы (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0db5a79f187cb0fe320bf67aace751a5d4c537d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359318"
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

