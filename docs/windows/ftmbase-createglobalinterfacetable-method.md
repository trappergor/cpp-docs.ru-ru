---
title: Метод FtmBase::CreateGlobalInterfaceTable | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable
dev_langs:
- C++
helpviewer_keywords:
- CreateGlobalInterfaceTable method
ms.assetid: bb82a0c5-22b9-4844-9204-7922033d8b07
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c042b6bd17da3459f499f9eb1c9167343c2e2ab
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578777"
---
# <a name="ftmbasecreateglobalinterfacetable-method"></a>Метод FtmBase::CreateGlobalInterfaceTable

Создает общую таблицу интерфейса (GIT).

## <a name="syntax"></a>Синтаксис

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Параметры

*Git*  
После завершения этой операции указатель на общую таблицу интерфейса.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе `IGlobalInterfaceTable` подразделы **COM-интерфейсы** подраздела **ссылку COM** раздела в библиотеке MSDN.

## <a name="requirements"></a>Требования

**Заголовок:** ftm.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Класс FtmBase](../windows/ftmbase-class.md)