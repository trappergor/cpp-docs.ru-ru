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
ms.openlocfilehash: e6c727993b2907aaa551421a5d2d23e372b68917
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319136"
---
# <a name="ca2caex-class"></a>Класс CA2CAEX

Этот класс используется макросами преобразования строк CA2CTEX и CT2CAEX, а также typedef CA2CA.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template<int t_nBufferLength = 128>
class CA2CAEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию составляет 128 байтов.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CA2CAEX::CA2CAEX](#ca2caex)|Конструктор.|
|[CA2CAEX: : CA2CAEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CA2CAEX:оператор LPCSTR](#operator_lpcstr)|Оператор конверсии.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CA2CAEX::m_psz](#m_psz)|Член данных, который хранит строку исходного кода.|

## <a name="remarks"></a>Remarks

Если не требуется дополнительная функциональность, используйте CA2CTEX, CT2CAEX или CA2CA в собственном коде.

Этот класс безопасен для использования в циклах и не будет переполнять стек. По умолчанию классы и макросы преобразования ATL используют для преобразования кодовую страницу ANSI текущего потока.

Следующие макросы основаны на этом классе:

- CA2CTEX

- CT2CAEX

Следующий тип основан на этом классе:

- CA2CA

Для обсуждения этих макросов преобразования текста [см.](string-conversion-macros.md)

## <a name="example"></a>Пример

Например, с помощью этих макросов преобразования строк можно ознакомиться на [atL и MFC String Conversion Macros.](string-conversion-macros.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

## <a name="ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX

Конструктор.

```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Текстовая строка, которая будет преобразована.

*nCodePage*<br/>
Не используется в этом классе.

### <a name="remarks"></a>Remarks

Создает буфер, необходимый для перевода.

## <a name="ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX: : CA2CAEX

Деструктор

```
~CA2CAEX() throw();
```

### <a name="remarks"></a>Remarks

Освобождает выделенный буфер.

## <a name="ca2caexm_psz"></a><a name="m_psz"></a>CA2CAEX::m_psz

Член данных, который хранит строку исходного кода.

```
LPCSTR m_psz;
```

## <a name="ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX:оператор LPCSTR

Оператор конверсии.

```
operator LPCSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку текста по типу LPCSTR.

## <a name="see-also"></a>См. также раздел

[Класс CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Класс CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Класс CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
