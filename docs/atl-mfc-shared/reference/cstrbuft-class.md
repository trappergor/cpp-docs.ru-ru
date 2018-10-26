---
title: Класс CStrBufT | Документация Майкрософт
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82152ea3df6bb21ee1405790acf9d3fb2c9630c5
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808996"
---
# <a name="cstrbuft-class"></a>Класс CStrBufT

Этот класс предоставляет автоматическое освобождение ресурстов для `GetBuffer` и `ReleaseBuffer` вызывает на существующем `CStringT` объекта.

## <a name="syntax"></a>Синтаксис

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>Параметры

*TCharType*<br/>
Тип символа для `CStrBufT` класса. Ниже указаны доступные значения.

- **char** (для символьных строк ANSI)

- **wchar_t** (для символьных строк в Юникоде)

- TCHAR (для символьных строк ANSI и Юникода)

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|PCXSTR|Указатель на строковую константу.|
|PXSTR|Указатель на строку.|
|`StringType`|Строковый тип, буфер которого должен управляться специализации этого класса шаблона.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStrBufT::CStrBufT](#cstrbuft)|Конструктор для объекта буфера строки.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStrBufT::SetLength](#setlength)|Задает длину буфера знаков соответствующий строковый объект.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CStrBufT::operator PCXSTR](#operator_pcxstr)|Извлекает **const** указатель на буфер символов соответствующий строковый объект.|
|[CStrBufT::operator PXSTR](#operator_pxstr)|Извлекает указатель на буфер символов соответствующий строковый объект.|

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[CStrBufT::AUTO_LENGTH](#auto_length)|Автоматически Определите новые длину строки на момент выпуска.|
|[CStrBufT::SET_LENGTH](#set_length)|Задайте длину строкового объекта во время GetBuffer|

## <a name="remarks"></a>Примечания

Этот класс используется как класс-оболочку для замены вызовов [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), или [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) и `ReleaseBuffer`.

В первую очередь созданы как вспомогательный класс `CStrBufT` предоставляет удобный способ работы с буфер символов строкового объекта, не беспокоясь о том, как разработчик или когда вызывать `ReleaseBuffer`. Это можно сделать, так как объект-оболочка выходит за пределы области, естественным образом в случае исключения или несколько существующих частей кода; вызывает деструктор для освобождения строкового ресурса.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpstr.h

##  <a name="auto_length"></a>  CStrBufT::AUTO_LENGTH

Автоматически Определите новые длину строки на момент выпуска.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>Примечания

Автоматически Определите новые длину строки на момент выпуска. Строка должна быть нулем.

##  <a name="cstrbuft"></a>  CStrBufT::CStrBufT

Создает объект буфера.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Строковый объект, связанный с буфером. Как правило, разработчик будет использовать предварительно заданных определений типов из `CStrBuf` (TCHAR вариант), `CStrBufA` (**char** вариант) и `CStrBufW` (**wchar_t** вариант).

*nMinLength*<br/>
Минимальная длина буфера знаков.

*dwFlags*<br/>
Определяет, если длина строки определяется автоматически. Ниже указаны доступные значения.

- Длина строки AUTO_LENGTH является автоматически определяется при [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) вызывается. Строка должна быть нулем. Значение по умолчанию.

- Длина строки SET_LENGTH задается, если [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) вызывается.

### <a name="remarks"></a>Примечания

Создает строковый буфер для соответствующий строковый объект. Во время построения [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) или [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) вызывается.

Обратите внимание, что конструктор копии **частного**.

##  <a name="operator_pcxstr"></a>  CStrBufT::operator PCXSTR

Напрямую обращается к символов, сохраненных в соответствующий строковый объект в виде строки C-стиля.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Символ указатель на строку данных.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для возврата указателя на буфер символов строкового объекта. Содержимое объекта string не может изменяться с помощью этого указателя.

##  <a name="operator_pxstr"></a>  CStrBufT::operator PXSTR

Напрямую обращается к символов, сохраненных в соответствующий строковый объект в виде строки C-стиля.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Символ указатель на строку данных.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию для возврата указателя на буфер символов строкового объекта. Разработчик может изменять содержимое объекта string с помощью этого указателя.

##  <a name="pcxstr"></a>  CStrBufT::PCXSTR

Указатель на строковую константу.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

##  <a name="pxstr"></a>  CStrBufT::PXSTR

Указатель на строку.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

##  <a name="set_length"></a>  CStrBufT::SET_LENGTH

Задайте длину строкового объекта в `GetBuffer` времени.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>Примечания

Задайте длину строкового объекта во время GetBuffer.

Определяет, если [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) вызываются при создании объекта буфера строки.

##  <a name="setlength"></a>  CStrBufT::SetLength

Задает длину буфера знаков.

```
void SetLength(int nLength);
```

### <a name="parameters"></a>Параметры

*nLength*<br/>
Новая длина буфера символ объекта строки.

> [!NOTE]
>  Должно быть меньше или равно длине минимальный размер буфера, указанный в конструкторе класса `CStrBufT`.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию, чтобы задать длину строки, представленные объектом буфера.

##  <a name="stringtype"></a>  CStrBufT::StringType

Строковый тип, буфер которого должен управляться специализации этого класса шаблона.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>Примечания

`TCharType` используется ли тип символа для специализации шаблона класса.

## <a name="see-also"></a>См. также

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)

