---
title: Класс RoInitializeWrapper | Документация Майкрософт
ms.custom: ''
ms.date: 05/20/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f5c47ac34d8b159e75acf672ba57ca8c1ebac1e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592833"
---
# <a name="roinitializewrapper-class"></a>Класс RoInitializeWrapper

Инициализирует среду выполнения Windows.

## <a name="syntax"></a>Синтаксис

```cpp
class RoInitializeWrapper
```

## <a name="remarks"></a>Примечания

**RoInitializeWrapper** — это удобный инструмент, который инициализирует среду выполнения Windows и возвращает значение HRESULT, указывающее, является ли операция выполнена успешно. Так как вызывает деструктор класса `::Windows::Foundation::Uninitialize`, экземпляры **RoInitializeWrapper** должен быть объявлен в области глобального или верхнего уровня.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор RoInitializeWrapper::RoInitializeWrapper](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|Инициализирует новый экземпляр класса **RoInitializeWrapper** класса.|
|[Деструктор RoInitializeWrapper::~RoInitializeWrapper](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|Удаляет текущий экземпляр **RoInitializeWrapper** класса.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[Оператор RoInitializeWrapper::HRESULT()](../windows/roinitializewrapper-hresult-parens-operator.md)|Возвращает значение HRESULT **RoInitializeWrapper** конструктор.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RoInitializeWrapper`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)