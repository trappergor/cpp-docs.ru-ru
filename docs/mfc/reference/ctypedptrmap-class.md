---
title: Ctypedptrmap-класс
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: 05689001f8c385191057a8dc824a508189a43f05
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266065"
---
# <a name="ctypedptrmap-class"></a>Ctypedptrmap-класс

Предоставляет типобезопасную "программу-оболочку" для объектов классов карты указателей `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`и `CMapStringToPtr`.

## <a name="syntax"></a>Синтаксис

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс для класса map типизированных указателей; должен быть классом карты указатель ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, или `CMapStringToPtr`).

*KEY*<br/>
Класс объекта, используемое в качестве ключа к схеме.

*ЗНАЧЕНИЕ*<br/>
Класс объекта, хранимый в сопоставлении.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для выполнения итерации.|
|[CTypedPtrMap::Lookup](#lookup)|Возвращает `KEY` на основе `VALUE`.|
|[CTypedPtrMap::RemoveKey](#removekey)|Удаляет элемент, указанный с помощью ключа.|
|[CTypedPtrMap::SetAt](#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CTypedPtrMap::operator \[ \]](#operator_at)|Вставляет элемент в схеме.|

## <a name="remarks"></a>Примечания

При использовании `CTypedPtrMap`, средство проверки типов C++ помогает устранить ошибки, вызванные типы несоответствие указателей.

Так как все `CTypedPtrMap` функции, встроенные, использование этого шаблона незначительно повлиять на размер или скорость кода.

Дополнительные сведения об использовании `CTypedPtrMap`, см. в статьях [коллекций](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

##  <a name="getnextassoc"></a>  CTypedPtrMap::GetNextAssoc

Извлекает элемент карты по `rNextPosition`, а затем обновляет `rNextPosition` для обращения к следующему элементу в сопоставлении.

```
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>Параметры

*rPosition*<br/>
Задает ссылку на значение ПОЗИЦИИ, возвращенное предыдущим `GetNextAssoc` или `BASE_CLASS` **:: GetStartPosition** вызова.

*KEY*<br/>
Параметр шаблона, указывающий тип карты ключей.

*rKey*<br/>
Указывает возвращаемый ключ полученного элемента.

*ЗНАЧЕНИЕ*<br/>
Параметр шаблона, указывающий тип значения карты.

*rValue*<br/>
Указывает возвращаемое значение полученного элемента.

### <a name="remarks"></a>Примечания

Эта функция наиболее полезна для перебора всех элементов в сопоставлении. Обратите внимание на то, что последовательность позиция не обязательно так же, как последовательности значение ключа.

Если полученного элемента является последним в сопоставлении, то новое значение `rNextPosition` имеет значение NULL.

Это встраиваемая функция вызывает `BASE_CLASS` **:: GetNextAssoc**.

##  <a name="lookup"></a>  CTypedPtrMap::Lookup

`Lookup` использует алгоритм хэширования для быстрого поиска элемента карты с ключом, обеспечивающее точное совпадение.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Параметр шаблона, указывающий базовый класс для класса этой карты.

*key*<br/>
Ключ элемента, который требуется найти.

*ЗНАЧЕНИЕ*<br/>
Параметр шаблона, указывающий тип значения, хранящиеся в данном сопоставлении.

*rValue*<br/>
Указывает возвращаемое значение полученного элемента.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент найден; в противном случае 0.

### <a name="remarks"></a>Примечания

Это встраиваемая функция вызывает `BASE_CLASS` **:: подстановки**.

##  <a name="operator_at"></a>  CTypedPtrMap::operator [ ]

Этот оператор может использоваться только в левой части оператора присваивания (l значение).

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>Параметры

*ЗНАЧЕНИЕ*<br/>
Параметр шаблона, указывающий тип значения, хранящиеся в данном сопоставлении.

*BASE_CLASS*<br/>
Параметр шаблона, указывающий базовый класс для класса этой карты.

*key*<br/>
Ключ элемента для поиска или создания в сопоставлении.

### <a name="remarks"></a>Примечания

Если ни один элемент карты с указанным ключом, то создается новый элемент. Нет нет» справа от оператора» (r-значение) эквивалентно этот оператор так как есть вероятность, что ключ не может находиться в схеме. Используйте `Lookup` функция-член для извлечения элемента.

##  <a name="removekey"></a>  CTypedPtrMap::RemoveKey

Эта функция-член вызывает `BASE_CLASS` **:: RemoveKey**.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>Параметры

*KEY*<br/>
Параметр шаблона, указывающий тип карты ключей.

*key*<br/>
Ключ элемента, который требуется удалить.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент был найден и успешно удален; в противном случае 0.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).

##  <a name="setat"></a>  CTypedPtrMap::SetAt

Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.

```
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>Параметры

*KEY*<br/>
Параметр шаблона, указывающий тип карты ключей.

*key*<br/>
Указывает значение ключа новое значение.

*новое значение*<br/>
Задает указатель на объект, который является значением нового элемента.

### <a name="remarks"></a>Примечания

Дополнительные примечания, см. в разделе [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).

## <a name="see-also"></a>См. также

[Пример MFC СБОР](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[Класс CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)<br/>
[Класс CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[Класс CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)
