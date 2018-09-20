---
title: Элемент данных Creatormap::factorycreator | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
dev_langs:
- C++
helpviewer_keywords:
- factoryCreator data member
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 12d4fdd415ab37c9af0b0b34651e7cd2f00cf31b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405285"
---
# <a name="creatormapfactorycreator-data-member"></a>Элемент данных CreatorMap::factoryCreator

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT (*factoryCreator)(
   unsigned int* currentflags,
   const CreatorMap* entry,
   REFIID iidClassFactory,
IUnknown** factory);
```

### <a name="parameters"></a>Параметры

*currentflags*<br/>
Один из [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) перечислителей.

*entry*<br/>
CreatorMap.

*iidClassFactory*<br/>
Идентификатор интерфейса фабрики класса.

*фабрики*<br/>
После завершения операции адрес фабрики класса.

## <a name="return-value"></a>Возвращаемое значение

Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.

## <a name="remarks"></a>Примечания

Создает фабрику для указанного объекта CreatorMap.

## <a name="requirements"></a>Требования

**Заголовок:** module.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура CreatorMap](../windows/creatormap-structure.md)<br/>
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)