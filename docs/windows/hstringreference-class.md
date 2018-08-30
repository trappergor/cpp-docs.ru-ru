---
title: Класс HStringReference | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference
dev_langs:
- C++
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4e3f7d59dd86aa15833134223854eb9ed01f6679
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216579"
---
# <a name="hstringreference-class"></a>Класс HStringReference

Представляет HSTRING, созданный из существующей строки.

## <a name="syntax"></a>Синтаксис

```cpp
class HStringReference;
```

## <a name="remarks"></a>Примечания

Время существования буфера резервного копирования в новом HSTRING не управляется средой выполнения Windows. Вызывающий объект выделяет строку источника в кадре стека во избежание выделения памяти для кучи и для исключения риска утечки памяти. Кроме того вызывающий объект должен убедиться, что строка источника остается неизменной в течение времени существования подключенного HSTRING. Дополнительные сведения см. в разделе [WindowsCreateStringReference функция](https://msdn.microsoft.com/0361bb7e-da49-4289-a93e-de7aab8712ac).

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор HStringReference::HStringReference](../windows/hstringreference-hstringreference-constructor.md)|Инициализирует новый экземпляр класса **HStringReference** класса.|

### <a name="members"></a>Участники

|Член|Описание:|
|------------|-----------------|
|[Метод HStringReference::CopyTo](../windows/hstringreference-copyto-method.md)|Копирует текущий **HStringReference** объект в объект HSTRING.|
|[Метод HStringReference::Get](../windows/hstringreference-get-method.md)|Получает значение базового дескриптора HSTRING.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[Оператор HStringReference::Operator=](../windows/hstringreference-operator-assign-operator.md)|Перемещает значение другого **HStringReference** объект с текущим **HStringReference** объекта.|
|[Оператор HStringReference::Operator==](../windows/hstringreference-operator-equality-operator.md)|Указывает, равны ли два параметра.|
|[Оператор HStringReference::Operator!=](../windows/hstringreference-operator-inequality-operator.md)|Указывает, действительно ли два параметра не равны.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HStringReference`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)