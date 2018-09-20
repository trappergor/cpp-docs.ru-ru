---
title: Handlet-класс | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT class
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6622e92112d9f73e673e2fb44598a393843bf0fa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396343"
---
# <a name="handlet-class"></a>HandleT - класс

Представляет дескриптор объекта.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename HandleTraits
>
class HandleT;
```

### <a name="parameters"></a>Параметры

*HandleTraits*<br/>
Экземпляр [HandleTraits](../windows/handletraits-structure.md) структура, которая определяет общие характеристики дескриптора.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`Traits`|Синоним для `HandleTraits`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор HandleT::HandleT](../windows/handlet-handlet-constructor.md)|Инициализирует новый экземпляр класса **HandleT** класса.|
|[Деструктор HandleT::~HandleT](../windows/handlet-tilde-handlet-destructor.md)|Отменяет инициализацию экземпляра **HandleT** класса.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод HandleT::Attach](../windows/handlet-attach-method.md)|Связывает указанный дескриптор с текущим **HandleT** объекта.|
|[Метод HandleT::Close](../windows/handlet-close-method.md)|Закрывает текущий **HandleT** объекта.|
|[Метод HandleT::Detach](../windows/handlet-detach-method.md)|Отсоединяет текущий **HandleT** объект из его базовый дескриптор.|
|[Метод HandleT::Get](../windows/handlet-get-method.md)|Возвращает значение базового дескриптора.|
|[Метод HandleT::IsValid](../windows/handlet-isvalid-method.md)|Указывает, является ли текущий **HandleT** представляет дескриптор.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[Метод HandleT::InternalClose](../windows/handlet-internalclose-method.md)|Закрывает текущий **HandleT** объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор HandleT::operator=](../windows/handlet-operator-assign-operator.md)|Перемещает значение указанного **HandleT** объект с текущим **HandleT** объекта.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание|
|----------|-----------------|
|[Элемент данных HandleT::handle_](../windows/handlet-handle-data-member.md)|Содержит дескриптор, представленного **HandleT** объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HandleT`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::wrl:: wrappers

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)