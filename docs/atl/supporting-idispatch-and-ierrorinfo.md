---
title: Поддержка IDispatch и IErrorInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d9c27dfe81c3bbd2978f418c8e942ac20190b30
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753612"
---
# <a name="supporting-idispatch-and-ierrorinfo"></a>Поддержка IDispatch и IErrorInfo

Можно использовать класс шаблона [IDispatchImpl](../atl/reference/idispatchimpl-class.md) для предоставления реализацию по умолчанию `IDispatch Interface` часть любого сдвоенные интерфейсы в объекте.

Если объект использует `IErrorInfo` интерфейс сообщить ошибок обратно клиенту, а затем ваш объект должен поддерживать `ISupportErrorInfo Interface` интерфейс. Класс шаблона [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) предоставляет простой способ выполнить это, если имеется только один интерфейс, который выдает ошибки для объекта.

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)

