---
title: Comptrref-класс | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4ec1139efae422035ef34030cfcffcc5547f0a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418506"
---
# <a name="comptrref-class"></a>ComPtrRef - класс

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename T
>
class ComPtrRef : public ComPtrRefBase<T>;
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Объект [ComPtr\<T >](../windows/comptr-class.md) тип или тип, производный от него, а не просто интерфейс, представленный `ComPtr`.

## <a name="remarks"></a>Примечания

Представляет ссылку на объект типа `ComPtr<T>`.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор ComPtrRef::ComPtrRef](../windows/comptrref-comptrref-constructor.md)|Инициализирует новый экземпляр класса **ComPtrRef** класс из заданного указателя в другой **ComPtrRef** объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод ComPtrRef::GetAddressOf](../windows/comptrref-getaddressof-method.md)|Извлекает адрес указателя на интерфейс, представленный текущим **ComPtrRef** объекта.|
|[Метод ComPtrRef::ReleaseAndGetAddressOf](../windows/comptrref-releaseandgetaddressof-method.md)|Удаляет текущий **ComPtrRef** и возвращает указатель на указатель на интерфейс, который был представлен **ComPtrRef** объекта.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[Оператор ComPtrRef::operator InterfaceType**](../windows/comptrref-operator-interfacetype-star-star-operator.md)|Удаляет текущий **ComPtrRef** и возвращает указатель на указатель на интерфейс, который был представлен **ComPtrRef** объекта.|
|[Оператор ComPtrRef::operator T*](../windows/comptrref-operator-t-star-operator.md)|Возвращает значение [ptr_](../windows/comptrrefbase-ptr-data-member.md) данными-членом текущим объектом ComPtrRef.|
|[Оператор ComPtrRef::operator void**](../windows/comptrref-operator-void-star-star-operator.md)|Удаляет текущий **ComPtrRef** объекта, приведение указателя на интерфейс, который был представлен **ComPtrRef** объекта как указатель к указатель to **void**, а затем Возвращает указатель приведения.|
|[Оператор ComPtrRef::operator*](../windows/comptrref-operator-star-operator.md)|Извлекает указатель на интерфейс, представленный текущим **ComPtrRef** объекта.|
|[Оператор ComPtrRef::operator==](../windows/comptrref-operator-equality-operator.md)|Указывает ли два **ComPtrRef** объекты равны.|
|[Оператор ComPtrRef::operator!=](../windows/comptrref-operator-inequality-operator.md)|Указывает ли два **ComPtrRef** объекты не равны.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtrRefBase`

`ComPtrRef`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)