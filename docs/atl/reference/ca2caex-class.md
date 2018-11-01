---
title: Класс CA2CAEX
ms.date: 11/04/2016
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
ms.openlocfilehash: 42115df5d70121d90631bf18c5d3fa83b130485b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487310"
---
# <a name="ca2caex-class"></a>Класс CA2CAEX

Этот класс используется, макросы преобразования строк CA2CTEX CT2CAEX и typedef CA2CA.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<int t_nBufferLength = 128>
class CA2CAEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию равен 128 байтам.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|Конструктор.|
|[CA2CAEX:: ~ CA2CAEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|Оператор преобразования.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CA2CAEX::m_psz](#m_psz)|Элемент данных, который хранит исходную строку.|

## <a name="remarks"></a>Примечания

Если дополнительные функциональные возможности не требуется, используйте CA2CTEX, CT2CAEX или CA2CA в собственном коде.

Этот класс можно безопасно использовать в циклах и не приводят к переполнению стека. По умолчанию классы и макросы преобразования ATL используют для преобразования кодовую страницу ANSI текущего потока.

Следующие макросы основаны на этот класс:

- CA2CTEX

- CT2CAEX

Следующие определения типа зависит от этого класса:

- CA2CA

Описание этих макросов текстового преобразования, см. в разделе [ATL и макросов преобразования MFC из строки](string-conversion-macros.md).

## <a name="example"></a>Пример

См. в разделе [ATL и макросы преобразования строк MFC](string-conversion-macros.md) пример использования эти макросы преобразования строк.

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

##  <a name="ca2caex"></a>  CA2CAEX::CA2CAEX

Конструктор.

```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*psz*<br/>
Текстовая строка для преобразования.

*nCodePage*<br/>
Не используется в этом классе.

### <a name="remarks"></a>Примечания

Создает буфер, необходимый для перевода.

##  <a name="dtor"></a>  CA2CAEX:: ~ CA2CAEX

Деструктор

```
~CA2CAEX() throw();
```

### <a name="remarks"></a>Примечания

Освобождает выделенный буфер.

##  <a name="m_psz"></a>  CA2CAEX::m_psz

Элемент данных, который хранит исходную строку.

```
LPCSTR m_psz;
```

##  <a name="operator_lpcstr"></a>  CA2CAEX::operator LPCSTR

Оператор преобразования.

```
operator LPCSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текстовую строку, как тип LPCSTR.

## <a name="see-also"></a>См. также

[Класс CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Класс CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Класс CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
