---
title: Класс ComPtr | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr class
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a20dd5e2fb43dd5caae7a5185260d8c88637d33
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597966"
---
# <a name="comptr-class"></a>Класс ComPtr

Создает тип *интеллектуальный указатель* , который представляет интерфейс, определяемый параметром шаблона. **ComPtr** автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равным нулю.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Параметры

*T*  
Интерфейс, **ComPtr** представляет.

*U*  
Класс, к которому текущий **ComPtr** является дружественной. (Шаблон, который использует этот параметр, защищен.)

## <a name="remarks"></a>Примечания

`ComPtr<>` Объявляет тип, представляющий указателя базового интерфейса. Используйте `ComPtr<>` объявления переменной, а затем использовать оператор доступа к членам в виде стрелки (`->`) для доступа к функция-член интерфейса.

Дополнительные сведения об интеллектуальных указателях см. подраздел «Интеллектуальные указатели COM» [COM Coding Practices](/windows/desktop/LearnWin32/com-coding-practices)раздела в библиотеке MSDN.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`InterfaceType`|Синоним для типа, заданного параметром *T* параметр шаблона.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Конструктор ComPtr::ComPtr](../windows/comptr-comptr-constructor.md)|Инициализирует новый экземпляр класса **ComPtr** класса. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.|
|[Деструктор ComPtr::~ComPtr](../windows/comptr-tilde-comptr-destructor.md)|Отменяет инициализацию экземпляра **ComPtr**.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[Метод ComPtr::As](../windows/comptr-as-method.md)|Возвращает **ComPtr** , представляющий интерфейс, определенный параметром указанного шаблона.|
|[Метод ComPtr::AsIID](../windows/comptr-asiid-method.md)|Возвращает **ComPtr** , представляющий интерфейс, определенный с помощью идентификатора указанного интерфейса.|
|[Метод ComPtr::AsWeak](../windows/comptr-asweak-method.md)|Извлекает слабую ссылку на текущий объект.|
|[Метод ComPtr::Attach](../windows/comptr-attach-method.md)|Это связывает **ComPtr** с типом интерфейса, указанным текущим параметром типа шаблона.|
|[Метод ComPtr::CopyTo](../windows/comptr-copyto-method.md)|Копирует текущий или указанный интерфейс, связанный с этим **ComPtr** в заданный выходной указатель.|
|[Метод ComPtr::Detach](../windows/comptr-detach-method.md)|Отменяет связь этого **ComPtr** с интерфейсом, который он представляет.|
|[Метод ComPtr::Get](../windows/comptr-get-method.md)|Извлекает указатель на интерфейс, который связан с данным **ComPtr**.|
|[Метод ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md)|Извлекает адрес [ptr_](../windows/comptr-ptr-data-member.md) элемент данных, который содержит указатель на интерфейс, представленный этим **ComPtr**.|
|[Метод ComPtr::ReleaseAndGetAddressOf](../windows/comptr-releaseandgetaddressof-method.md)|Освобождает интерфейс, связанный с данным **ComPtr** , а затем извлекает адрес [ptr_](../windows/comptr-ptr-data-member.md) элемент данных, который содержит указатель на интерфейс, который был выпущен.|
|[ComPtr::Reset](../windows/comptr-reset.md)|Освобождает все ссылки на указатель на интерфейс, который связан с данным **ComPtr**.|
|[Метод ComPtr::Swap](../windows/comptr-swap-method.md)|Меняет местами интерфейс, управляемый текущим **ComPtr** с помощью интерфейса, управляемого с помощью указанного **ComPtr**.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание:|
|----------|-----------------|
|[Метод ComPtr::InternalAddRef](../windows/comptr-internaladdref-method.md)|Увеличивает счетчик ссылок интерфейса, связанного с данным **ComPtr**.|
|[Метод ComPtr::InternalRelease](../windows/comptr-internalrelease-method.md)|Выполняет операцию освобождения модели COM в интерфейсе, связанном с этим **ComPtr**.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[Оператор ComPtr::operator Microsoft::WRL::Details::BoolType](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|Указывает ли **ComPtr** управление временем существования объектов интерфейса.|
|[Оператор ComPtr::operator&](../windows/comptr-operator-ampersand-operator.md)|Извлекает адрес текущего **ComPtr**.|
|[Оператор ComPtr::operator=](../windows/comptr-operator-assign-operator.md)|Присваивает значение текущему **ComPtr**.|
|[Оператор ComPtr::operator->](../windows/comptr-operator-arrow-operator.md)|Извлекает указатель на тип, заданный текущим параметром шаблона.|
|[Оператор ComPtr::operator==](../windows/comptr-operator-equality-operator.md)|Указывает ли два **ComPtr** объекты равны.|
|[Оператор ComPtr::operator!=](../windows/comptr-operator-inequality-operator.md)|Указывает ли два **ComPtr** объекты не равны.|

### <a name="protected-data-members"></a>Защищенные члены данных

|name|Описание:|
|----------|-----------------|
|[Элемент данных ComPtr::ptr_](../windows/comptr-ptr-data-member.md)|Содержит указатель на интерфейс, который связан с и управляемые этим экземпляром **ComPtr**.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ComPtr`

## <a name="requirements"></a>Требования

**Заголовок:** client.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)