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
ms.openlocfilehash: 927b9f5031bb6262c2f4a071b535802eb9e6990a
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497952"
---
# <a name="ca2wex-class"></a>Класс CA2WEX

Этот класс используется макросами преобразования строк CA2TEX, CA2CTEX, CT2WEX и CT2CWEX и typedef CA2W.

> [!IMPORTANT]
>  Этот класс и его члены не могут использоваться в приложениях, выполняемых в среда выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <int t_nBufferLength = 128>
class CA2WEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию составляет 128 байт.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CA2WEX::CA2WEX](#ca2wex)|Конструктор.|
|[CA2WEX:: ~ CA2WEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[CA2WEX:: operator LPWSTR](#operator_lpwstr)|Оператор преобразования.|

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CA2WEX::m_psz](#m_psz)|Элемент данных, в котором хранится исходная строка.|
|[CA2WEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованной строки.|

## <a name="remarks"></a>Примечания

Если не требуется дополнительных функций, используйте в коде CA2TEX, CA2CTEX, CT2WEX, CT2CWEX или CA2W.

Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком велик для использования в статическом буфере, класс выделяет память с помощью функции **malloc**, освобождая память, когда объект выходит из области. Это гарантирует, что, в отличие от макросов преобразования текста, доступных в предыдущих версиях ATL, этот класс можно использовать в циклах, и он не будет переполнен стек.

Если класс пытается выделить память в куче и завершается ошибкой, он будет вызываться `AtlThrow` с аргументом E_OUTOFMEMORY.

По умолчанию классы и макросы преобразования ATL используют для преобразования кодовую страницу ANSI текущего потока. Если вы хотите переопределить это поведение для конкретного преобразования, укажите кодовую страницу в качестве второго параметра для конструктора класса.

Следующие макросы основаны на этом классе:

- CA2TEX

- CA2CTEX

- CT2WEX

- CT2CWEX

Следующий typedef основан на этом классе:

- CA2W

Обсуждение этих макросов преобразования текста см. в разделе [ATL и макросы преобразования строк MFC](string-conversion-macros.md).

## <a name="example"></a>Пример

Пример использования этих макросов преобразования строк см. в разделе [ATL и макросы преобразования строк MFC](string-conversion-macros.md) .

## <a name="requirements"></a>Требования

**Заголовок:** атлконв. h

##  <a name="ca2wex"></a>CA2WEX::CA2WEX

Конструктор.

```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*псз*<br/>
Текстовая строка для преобразования.

*нкодепаже*<br/>
Кодовая страница, используемая для выполнения преобразования. Дополнительные сведения см. в обсуждении параметров кодовой страницы для функции Windows SDK [MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar) .

### <a name="remarks"></a>Примечания

Выделяет буфер, используемый в процессе перевода.

##  <a name="dtor"></a>CA2WEX:: ~ CA2WEX

Деструктор

```
~CA2WEX() throw();
```

### <a name="remarks"></a>Примечания

Освобождает выделенный буфер.

##  <a name="m_psz"></a>CA2WEX::m_psz

Элемент данных, в котором хранится исходная строка.

```
LPWSTR m_psz;
```

##  <a name="m_szbuffer"></a>CA2WEX::m_szBuffer

Статический буфер, используемый для хранения преобразованной строки.

```
wchar_t m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpwstr"></a>CA2WEX:: operator LPWSTR

Оператор преобразования.

```
operator LPWSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текстовую строку типа LPWSTR.

## <a name="see-also"></a>См. также

[Класс CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Класс CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Класс CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Обзор класса](../../atl/atl-class-overview.md)
