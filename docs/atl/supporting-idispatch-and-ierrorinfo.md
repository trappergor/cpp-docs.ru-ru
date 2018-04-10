---
title: Поддержка IDispatch и IErrorInfo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IErrorInfo
- IDispatch
dev_langs:
- C++
helpviewer_keywords:
- ISupportErrorInfoImpl method
- IErrorInfo class suppor in ATL
- IDispatchImpl class
- IDispatch class support in ATL
ms.assetid: 7db2220f-319d-4ce9-9382-d340019f14f7
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f39db3e844df884e8e95352bed2a078b01beede8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>Поддержка IDispatch и IErrorInfo
Класс шаблона можно использовать [IDispatchImpl](../atl/reference/idispatchimpl-class.md) для реализации по умолчанию из `IDispatch Interface` часть любых двух интерфейсов объекта.  
  
 Если объект использует `IErrorInfo` отчетов ошибок обратно клиенту, то объект должен поддерживать интерфейс `ISupportErrorInfo Interface` интерфейс. Класс шаблона [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) позволяет легко реализовать это, если имеется только один интерфейс, который приводит к возникновению ошибки в объекте.  
  
## <a name="see-also"></a>См. также  
 [Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)

