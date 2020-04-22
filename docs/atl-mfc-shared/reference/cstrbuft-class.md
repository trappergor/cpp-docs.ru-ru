---
title: Класс CStrBufT
ms.date: 10/18/2018
f1_keywords:
- CStrBufT
- ATLSIMPSTR/ATL::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::CStrBufT
- ATLSIMPSTR/ATL::CStrBufT::SetLength
- ATLSIMPSTR/ATL::CStrBufT::AUTO_LENGTH
- ATLSIMPSTR/ATL::CStrBufT::SET_LENGTH
helpviewer_keywords:
- strings [C++], custom memory management
- CStrBufT class
- shared classes, CStrBufT
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
ms.openlocfilehash: 71d7b6f7d53e9613b1ac26013d73c1dbd1ef0aab
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746928"
---
# <a name="cstrbuft-class"></a>Класс CStrBufT

Этот класс обеспечивает автоматическую `GetBuffer` `ReleaseBuffer` очистку ресурсов `CStringT` и вызовы на существующий объект.

## <a name="syntax"></a>Синтаксис

```
template<typename TCharType>
class CStrBufT
```

#### <a name="parameters"></a>Параметры

*TCharType*<br/>
Тип персонажа `CStrBufT` класса. Может применяться один из перечисленных ниже типов.

- **символ** (для строк anSI символов)

- **wchar_t** (для строк символов Unicode)

- TCHAR (для строк символов ANSI и Unicode)

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|PCXSTR|Указатель на постоянную строку.|
|PXSTR|Указатель на строку.|
|`StringType`|Тип строки, буфером которого должны манипулировать специализации этого шаблона класса.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CStrBufT::CStrBufT](#cstrbuft)|Конструктор для объекта буфера строки.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CStrBufT::SetLength](#setlength)|Устанавливает длину буфера символов связанного объекта строки.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CStrBufT:Оператор PCXSTR](#operator_pcxstr)|Извлекает **указатель** конст-указателя на буфер символов связанного объекта строки.|
|[CStrBufT::оператор PXSTR](#operator_pxstr)|Извлекает указатель на буфер символов связанного объекта строки.|

### <a name="public-constants"></a>Открытые константы

|Имя|Описание|
|----------|-----------------|
|[CStrBufT::AUTO_LENGTH](#auto_length)|Автоматически определите новую длину строки при выпуске.|
|[CStrBufT::SET_LENGTH](#set_length)|Установите длину объекта строки во время GetBuffer|

## <a name="remarks"></a>Remarks

Этот класс используется в качестве обертки класса для замены вызовов [GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [ReleaseBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer), или [GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) и `ReleaseBuffer`.

В первую очередь разработан `CStrBufT` в качестве помощника класса, обеспечивает удобный способ для разработчика для работы с символом буфера строки объекта, не беспокоясь о том, как и когда звонить `ReleaseBuffer`. Это возможно, потому что объект обертки естественно выходит из сферы применения в случае исключения или нескольких путей выхода кода; в результате чего его деструктор, чтобы освободить строку ресурса.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpstr.h

## <a name="cstrbuftauto_length"></a><a name="auto_length"></a>CStrBufT::AUTO_LENGTH

Автоматически определите новую длину строки при выпуске.

```
static const DWORD AUTO_LENGTH = 0x01;
```

### <a name="remarks"></a>Remarks

Автоматически определите новую длину строки при выпуске. Строка должна быть нулевым.

## <a name="cstrbuftcstrbuft"></a><a name="cstrbuft"></a>CStrBufT::CStrBufT

Строит буферный объект.

```
CStrBufT(StringType& str, int nMinLength, DWORD dwFlags = AUTO_LENGTH) throw(...);
explicit CStrBufT(StringType& str) throw(...);
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Объект строки, связанный с буфером. Как правило, разработчик использует предопределенные `CStrBuf` типофы `CStrBufA` (вариант TCHAR), (вариант**char)** и `CStrBufW` **(wchar_t** вариант).

*nMinLength*<br/>
Минимальная длина буфера символов.

*dwFlags*<br/>
Определяет, определяется ли длина строки автоматически. Может применяться один из перечисленных ниже типов.

- AUTO_LENGTH длина строки автоматически определяется, когда [CSimpleStringT::Release](../../atl-mfc-shared/reference/csimplestringt-class.md#releasebuffer) вызывается. Строка должна быть нулевым. Значение по умолчанию.

- SET_LENGTH длина строки устанавливается, когда [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) называется.

### <a name="remarks"></a>Remarks

Создает буфер строки для связанного объекта строки. Во время строительства, [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) или [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) называется.

Обратите внимание, что конвейер является **частным.**

## <a name="cstrbuftoperator-pcxstr"></a><a name="operator_pcxstr"></a>CStrBufT:Оператор PCXSTR

Непосредственно получает доступ к символам, хранящимся в связанном объекте строки, как строка C-стиля.

```
operator PCXSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель символов к данным строки.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы вернуть указатель в буфер символов объекта строки. Содержимое объекта строки не может быть изменено с помощью этого указателя.

## <a name="cstrbuftoperator-pxstr"></a><a name="operator_pxstr"></a>CStrBufT::оператор PXSTR

Непосредственно получает доступ к символам, хранящимся в связанном объекте строки, как строка C-стиля.

```
operator PXSTR() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель символов к данным строки.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы вернуть указатель в буфер символов объекта строки. Разработчик может изменить содержимое объекта строки с помощью этого указателя.

## <a name="cstrbuftpcxstr"></a><a name="pcxstr"></a>CStrBufT::PCXSTR

Указатель на постоянную строку.

```
typedef CSimpleStringT<TCharType>::PCXSTR PCXSTR;
```

## <a name="cstrbuftpxstr"></a><a name="pxstr"></a>CStrBufT::PXSTR

Указатель на строку.

```
typedef CSimpleStringT<TCharType>::PXSTR PXSTR;
```

## <a name="cstrbuftset_length"></a><a name="set_length"></a>CStrBufT::SET_LENGTH

Установите длину объекта `GetBuffer` строки вовремя.

```
static const DWORD SET_LENGTH = 0x02;
```

### <a name="remarks"></a>Remarks

Установите длину объекта строки во время GetBuffer.

Определяет, если [CSimpleStringT::GetBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffer) и [CSimpleStringT::GetBufferSetLength](../../atl-mfc-shared/reference/csimplestringt-class.md#getbuffersetlength) называются, когда объект буфера строки построен.

## <a name="cstrbuftsetlength"></a><a name="setlength"></a>CStrBufT::SetLength

Устанавливает длину буфера символов.

```cpp
void SetLength(int nLength);
```

### <a name="parameters"></a>Параметры

*nДлина*<br/>
Новая длина буфера символов объекта строки.

> [!NOTE]
> Должна быть меньше или равна минимальной длине `CStrBufT`буфера, указанной в конструкторе.

### <a name="remarks"></a>Remarks

Вызовите эту функцию, чтобы установить длину строки, представленной буферным объектом.

## <a name="cstrbuftstringtype"></a><a name="stringtype"></a>CStrBufT::StringType

Тип строки, буфером которого должны манипулировать специализации этого шаблона класса.

```
typedef CSimpleStringT<TCharType> StringType;
```

### <a name="remarks"></a>Remarks

`TCharType`— это тип символов, используемый для специализации шаблона класса.

## <a name="see-also"></a>См. также раздел

[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Общие классы ATL/MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)
