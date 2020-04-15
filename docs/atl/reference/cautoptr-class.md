---
title: Класс CAutoPtr
ms.date: 11/04/2016
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
ms.openlocfilehash: cb8e3d6b71db6ab60b3b246bd8c5bf4f2c9aaa34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321256"
---
# <a name="cautoptr-class"></a>Класс CAutoPtr

Этот класс представляет собой интеллектуальный объект указателя.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <typename T>
class CAutoPtr
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип указателя.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAutoPtr::CAutoPtr](#cautoptr)|Конструктор.|
|[CAutoPtr:::](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAutoPtr::Attach](#attach)|Вызовите этот метод, чтобы взять на себя ответственность за существующий указатель.|
|[CAutoPtr::Detach](#detach)|Вызовите этот метод, чтобы освободить право собственности на указатель.|
|[CAutoPtr::Бесплатно](#free)|Вызовите этот метод, чтобы `CAutoPtr`удалить объект, на который указывает .|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAutoPtr:оператор ТЗ](#operator_t_star)|Оператор актерского состава.|
|[CAutoPtr::оператор](#operator_eq)|Оператор назначения.|
|[CAutoPtr:оператор ->](#operator_ptr)|Оператор указателя на участника.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CAutoPtr::m_p](#m_p)|Переменная данных указателя.|

## <a name="remarks"></a>Remarks

Этот класс предоставляет методы создания и управления интеллектуальным указателем, которые помогут защититься от утечек памяти, автоматически освобождая ресурсы, когда она выпадает из сферы действия.

Кроме `CAutoPtr`того, 's копию конструктора и уступки оператора передачи собственности указателя, копирование указателя источника на указатель назначения и установка указателя источника на NULL. Поэтому невозможно иметь два `CAutoPtr` объекта, каждый из которых хранения одного и того же указателя, и это уменьшает возможность удалять один и тот же указатель дважды.

`CAutoPtr`также упрощает создание коллекций указателей. Вместо того, чтобы вырабатывать класс коллекции и переопределяет разрушающий, проще `CAutoPtr` сделать коллекцию объектов. Когда коллекция удаляется, `CAutoPtr` объекты выходят из сферы действия и автоматически удаляются.

[CHeapPtr](../../atl/reference/cheapptr-class.md) и варианты работают `CAutoPtr`так же, как , за исключением того, что они выделяют и свободной памяти, используя различные функции кучи вместо **новых** и **удалить** операторов. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) похож `CAutoPtr`на , с той лишь разницей, что он использует **вектор ный** и **векторное удаление** для выделения и свободной памяти.

Смотрите также [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) и [CAutoPtrList,](../../atl/reference/cautoptrlist-class.md) когда требуются массивы или списки интеллектуальных указателей.

## <a name="requirements"></a>Требования

**Заголовок:** atlbase.h

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]

## <a name="cautoptrattach"></a><a name="attach"></a>CAutoPtr::Attach

Вызовите этот метод, чтобы взять на себя ответственность за существующий указатель.

```
void Attach(T* p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Объект `CAutoPtr` будет владеть этим указателем.

### <a name="remarks"></a>Remarks

Когда `CAutoPtr` объект становится владельцем указателя, он автоматически удаляет указатель и любые выделенные данные, когда он выходит за рамки. Если [cAutoPtr::Detach](#detach) называется, программист снова получает ответственность за освобождение любых выделенных ресурсов.

В отладочных сборках произойдет сбой утверждения, если [cAutoPtr::m_p](#m_p) элемент данных в настоящее время указывает на существующее значение; то есть, он не равен NULL.

### <a name="example"></a>Пример

Смотрите пример в [обзоре CAutoPtr.](../../atl/reference/cautoptr-class.md)

## <a name="cautoptrcautoptr"></a><a name="cautoptr"></a>CAutoPtr::CAutoPtr

Конструктор.

```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<>
CAutoPtr(CAutoPtr<T>& p) throw();
```

### <a name="parameters"></a>Параметры

*P*<br/>
Существующий указатель.

*TSrc*<br/>
Тип, управляемый `CAutoPtr`другим, используется для инициализации текущего объекта.

### <a name="remarks"></a>Remarks

Объект `CAutoPtr` может быть создан с помощью существующего указателя, и в этом случае он передает право собственности на указатель.

### <a name="example"></a>Пример

Смотрите пример в [обзоре CAutoPtr.](../../atl/reference/cautoptr-class.md)

## <a name="cautoptrcautoptr"></a><a name="dtor"></a>CAutoPtr:::

Деструктор

```
~CAutoPtr() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все выделенные ресурсы. Звонит [CAutoPtr::Бесплатно](#free).

## <a name="cautoptrdetach"></a><a name="detach"></a>CAutoPtr::Detach

Вызовите этот метод, чтобы освободить право собственности на указатель.

```
T* Detach() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает копию указателя.

### <a name="remarks"></a>Remarks

Выпускает право собственности на указатель, устанавливает [cAutoPtr::m_p](#m_p) переменной данных в NULL и возвращает копию указателя. После `Detach`вызова программист должен освободить все выделенные ресурсы, над которыми `CAutoPtr` объект, возможно, ранее предполагал репонируемость.

### <a name="example"></a>Пример

Смотрите пример в [обзоре CAutoPtr.](../../atl/reference/cautoptr-class.md)

## <a name="cautoptrfree"></a><a name="free"></a>CAutoPtr::Бесплатно

Вызовите этот метод, чтобы `CAutoPtr`удалить объект, на который указывает .

```
void Free() throw();
```

### <a name="remarks"></a>Remarks

Объект, на который `CAutoPtr` указывается, освобождается, и [cAutoPtr::m_p](#m_p) переменной члена данных установлен в NULL.

## <a name="cautoptrm_p"></a><a name="m_p"></a>CAutoPtr::m_p

Переменная данных указателя.

```
T* m_p;
```

### <a name="remarks"></a>Remarks

Эта переменная члена содержит информацию указателя.

## <a name="cautoptroperator-"></a><a name="operator_eq"></a>CAutoPtr::оператор

Оператор назначения.

```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```

### <a name="parameters"></a>Параметры

*P*<br/>
Указатель.

*TSrc*<br/>
Тип класса.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на **CAutoPtr\< T >**.

### <a name="remarks"></a>Remarks

Оператор назначения отсоединяет `CAutoPtr` объект от любого текущего указателя и прикрепляет новый указатель, *р,* на своем месте.

### <a name="example"></a>Пример

Смотрите пример в [обзоре CAutoPtr.](../../atl/reference/cautoptr-class.md)

## <a name="cautoptroperator--gt"></a><a name="operator_ptr"></a>CAutoPtr:оператор -&gt;

Оператор указателя на участника.

```
T* operator->() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение переменной [CAutoPtr::m_p](#m_p) данных.

### <a name="remarks"></a>Remarks

Используйте этот оператор для вызова метода `CAutoPtr` в классе, на который указывает объект. В сборках отладки произойдет `CAutoPtr` сбой утверждения, если точки NULL.

### <a name="example"></a>Пример

Смотрите пример в [обзоре CAutoPtr.](../../atl/reference/cautoptr-class.md)

## <a name="cautoptroperator-t"></a><a name="operator_t_star"></a>CAutoPtr:оператор ТЗ

Оператор актерского состава.

```
operator T* () const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на тип данных объекта, определенный в шаблоне класса.

### <a name="example"></a>Пример

Смотрите пример в [обзоре CAutoPtr.](../../atl/reference/cautoptr-class.md)

## <a name="see-also"></a>См. также раздел

[Класс CHeapPtr](../../atl/reference/cheapptr-class.md)<br/>
[Класс CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
