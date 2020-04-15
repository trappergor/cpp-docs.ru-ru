---
title: Класс CA2AEX
ms.date: 11/04/2016
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
ms.openlocfilehash: 4f8b9f91e9bc499523fe3484bc76325e2efb8140
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319185"
---
# <a name="ca2aex-class"></a>Класс CA2AEX

Этот класс используется макросами преобразования строк CA2TEX и CT2AEX, а также typedef CA2A.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <int t_nBufferLength = 128>
class CA2AEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию составляет 128 байтов.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CA2AEX:CA2AEX](#ca2aex)|Конструктор.|
|[CA2AEX:: CA2AEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CA2AEX::оператор LPSTR](#operator_lpstr)|Оператор конверсии.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CA2AEX::m_psz](#m_psz)|Член данных, который хранит строку исходного кода.|
|[CA2AEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованной строки.|

## <a name="remarks"></a>Remarks

Если не требуется дополнительная функциональность, используйте CA2TEX, CT2AEX или CA2A в собственном коде.

Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком велик, чтобы поместиться в статический буфер, класс выделяет память с помощью **malloc,** освобождая память, когда объект выходит из области. Это гарантирует, что, в отличие от макросов преобразования текста, доступных в предыдущих версиях ATL, этот класс безопасен для использования в циклах и что он не будет переполнять стек.

Если класс пытается выделить память на кучу и не `AtlThrow` удается, он будет звонить с аргументом E_OUTOFMEMORY.

По умолчанию классы и макросы конверсии ATL используют для преобразования страницу кода ANSI текущего потока.

Следующие макросы основаны на этом классе:

- CA2TEX

- CT2AEX

Следующий тип основан на этом классе:

- CA2A

Для обсуждения этих макросов преобразования текста [см.](string-conversion-macros.md)

## <a name="example"></a>Пример

Например, с помощью этих макросов преобразования строк можно ознакомиться на [atL и MFC String Conversion Macros.](string-conversion-macros.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

## <a name="ca2aexca2aex"></a><a name="ca2aex"></a>CA2AEX:CA2AEX

Конструктор.

```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Текстовая строка, которая будет преобразована.

*nCodePage*<br/>
Не используется в этом классе.

### <a name="remarks"></a>Remarks

Создает буфер, необходимый для перевода.

## <a name="ca2aexca2aex"></a><a name="dtor"></a>CA2AEX:: CA2AEX

Деструктор

```
~CA2AEX() throw();
```

### <a name="remarks"></a>Remarks

Освобождает выделенный буфер.

## <a name="ca2aexm_psz"></a><a name="m_psz"></a>CA2AEX::m_psz

Член данных, который хранит строку исходного кода.

```
LPSTR m_psz;
```

## <a name="ca2aexm_szbuffer"></a><a name="m_szbuffer"></a>CA2AEX::m_szBuffer

Статический буфер, используемый для хранения преобразованной строки.

```
char m_szBuffer[ t_nBufferLength];
```

## <a name="ca2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CA2AEX::оператор LPSTR

Оператор конверсии.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку текста по типу LPSTR.

## <a name="see-also"></a>См. также раздел

[Класс CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Класс CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Класс CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
