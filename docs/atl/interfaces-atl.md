---
title: Интерфейсы (ATL) | Документация Майкрософт
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
ms.openlocfilehash: 1410a437d87b56b244eb4fcd711797c279bec446
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217887"
---
# <a name="interfaces-atl"></a>Интерфейсы (ATL)
Интерфейс является способом, в котором объект предоставляющее свои функции с внешним миром. В модели COM интерфейс — это таблица указателей (таких как C++ vtable) для функций, реализованных данным объектом. Таблица представляет интерфейс, и функции, на которые он указывает являются методы этого интерфейса. Объект может предоставлять любое количество интерфейсов, он выбирает.  
  
 Каждый интерфейс основан на основной интерфейс COM, [IUnknown](../atl/iunknown.md). Методы класса `IUnknown` позволяют осуществлять переход на другие интерфейсы, предоставляемые объектом.  
  
 Кроме того каждый интерфейс присваивается уникальный идентификатора интерфейса (IID). Эта уникальность упрощает для поддержки управления версиями интерфейса. Новая версия интерфейса — это просто новый интерфейс, с помощью нового IID.  
  
> [!NOTE]
>  Идентификаторы IID для стандартных интерфейсов COM и OLE предопределены.  
  
## <a name="see-also"></a>См. также  
 [Введение в модель COM](../atl/introduction-to-com.md)   
 [COM-объекты и интерфейсы](/windows/desktop/com/com-objects-and-interfaces)

