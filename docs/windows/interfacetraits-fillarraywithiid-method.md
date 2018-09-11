---
title: Метод InterfaceTraits::FillArrayWithIid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: 73583177-adc9-4fcb-917d-fa7e6d07c990
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fc4679d9e6d3a4fdfc112d8a8b471ceb2646ecc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583732"
---
# <a name="interfacetraitsfillarraywithiid-method"></a>Метод InterfaceTraits::FillArrayWithIid

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
__forceinline static void FillArrayWithIid(
   _Inout_ unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Параметры

*Индекс*  
Указатель на поле, содержащее значение отсчитываемый от нуля индекс.

*идентификаторы IID*  
Массив идентификаторов интерфейсов.

## <a name="remarks"></a>Примечания

Назначает идентификатор интерфейса `Base` к элементу массива, указанного аргументом индекса.

В отличие от имени этого API только один массив изменяется; не весь массив.

Дополнительные сведения о `Base`, см. в разделе общедоступные определения типов в [interfacetraits-структура](../windows/interfacetraits-structure.md).

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура InterfaceTraits](../windows/interfacetraits-structure.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)