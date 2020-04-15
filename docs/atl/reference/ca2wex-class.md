---
title: Класс CA2WEX
ms.date: 11/04/2016
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
ms.openlocfilehash: c9123e163ca828fa71fe217e46537ceb18e6f549
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319131"
---
# <a name="ca2wex-class"></a>Класс CA2WEX

Этот класс используется макросами преобразования строк CA2TEX, CA2CTEX, CT2WEX и CT2CWEX, а также typedef CA2W.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
template <int t_nBufferLength = 128>
class CA2WEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию составляет 128 байтов.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CA2WEX:CA2WEX](#ca2wex)|Конструктор.|
|[CA2WEX::CA2WEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CA2WEX:Оператор LPWSTR](#operator_lpwstr)|Оператор конверсии.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CA2WEX::m_psz](#m_psz)|Член данных, который хранит строку исходного кода.|
|[CA2WEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованной строки.|

## <a name="remarks"></a>Remarks

Если не требуется дополнительная функциональность, используйте CA2TEX, CA2CTEX, CT2WEX, CT2CWEX или CA2W в коде.

Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком велик, чтобы поместиться в статический буфер, класс выделяет память с помощью **malloc,** освобождая память, когда объект выходит из области. Это гарантирует, что, в отличие от макросов преобразования текста, доступных в предыдущих версиях ATL, этот класс безопасен для использования в циклах и что он не будет переполнять стек.

Если класс пытается выделить память на кучу и не `AtlThrow` удается, он будет звонить с аргументом E_OUTOFMEMORY.

По умолчанию классы и макросы конверсии ATL используют для преобразования страницу кода ANSI текущего потока. Если требуется переопределить это поведение для определенного преобразования, укажите страницу кода в качестве второго параметра для конструктора для класса.

Следующие макросы основаны на этом классе:

- CA2TEX

- CA2CTEX

- CT2WEX

- CT2CWEX

Следующий тип основан на этом классе:

- CA2W

Для обсуждения этих макросов преобразования текста [см.](string-conversion-macros.md)

## <a name="example"></a>Пример

Например, с помощью этих макросов преобразования строк можно ознакомиться на [atL и MFC String Conversion Macros.](string-conversion-macros.md)

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

## <a name="ca2wexca2wex"></a><a name="ca2wex"></a>CA2WEX:CA2WEX

Конструктор.

```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*Psz*<br/>
Текстовая строка, которая будет преобразована.

*nCodePage*<br/>
Страница кода, используемая для выполнения преобразования. Более подробную информацию можно узнать о обсуждении параметров страницы кода для функции Windows SDK [MultiByteToWideChar.](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)

### <a name="remarks"></a>Remarks

Выделяет буфер, используемый в процессе перевода.

## <a name="ca2wexca2wex"></a><a name="dtor"></a>CA2WEX::CA2WEX

Деструктор

```
~CA2WEX() throw();
```

### <a name="remarks"></a>Remarks

Освобождает выделенный буфер.

## <a name="ca2wexm_psz"></a><a name="m_psz"></a>CA2WEX::m_psz

Член данных, который хранит строку исходного кода.

```
LPWSTR m_psz;
```

## <a name="ca2wexm_szbuffer"></a><a name="m_szbuffer"></a>CA2WEX::m_szBuffer

Статический буфер, используемый для хранения преобразованной строки.

```
wchar_t m_szBuffer[t_nBufferLength];
```

## <a name="ca2wexoperator-lpwstr"></a><a name="operator_lpwstr"></a>CA2WEX:Оператор LPWSTR

Оператор конверсии.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает строку текста по типу LPWSTR.

## <a name="see-also"></a>См. также раздел

[Класс CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Класс CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Класс CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
