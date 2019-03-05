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
ms.openlocfilehash: 712e663ab58e2c9de4e2f25090b84b35d0bced71
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293827"
---
# <a name="ca2aex-class"></a>Класс CA2AEX

Этот класс используется, макросы преобразования строк CA2TEX CT2AEX и typedef CA2A.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template <int t_nBufferLength = 128>
class CA2AEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию равен 128 байтам.

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CA2AEX::CA2AEX](#ca2aex)|Конструктор.|
|[CA2AEX:: ~ CA2AEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[CA2AEX::operator LPSTR](#operator_lpstr)|Оператор преобразования.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CA2AEX::m_psz](#m_psz)|Элемент данных, который хранит исходную строку.|
|[CA2AEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованную строку.|

## <a name="remarks"></a>Примечания

Если дополнительные функциональные возможности не требуется, используйте CA2TEX, CT2AEX или CA2A в собственном коде.

Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком велик для помещения в статический буфер, класс выделяет память с помощью **malloc**, освободить память, когда объект выходит за пределы области действия. Это гарантирует, что, в отличие от текста макросы преобразования, доступных в предыдущих версиях библиотеки ATL, этот класс можно безопасно использовать в циклах, и что он не приводят к переполнению стека.

Если класс пытается выделить память для кучи и происходит сбой, он вызывает `AtlThrow` с аргументом E_OUTOFMEMORY.

По умолчанию ATL классы и макросы преобразования используют кодовую страницу ANSI текущего потока для преобразования.

Следующие макросы основаны на этот класс:

- CA2TEX

- CT2AEX

Следующие определения типа зависит от этого класса:

- CA2A

Описание этих макросов текстового преобразования, см. в разделе [ATL и макросов преобразования MFC из строки](string-conversion-macros.md).

## <a name="example"></a>Пример

См. в разделе [ATL и макросы преобразования строк MFC](string-conversion-macros.md) пример использования эти макросы преобразования строк.

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

##  <a name="ca2aex"></a>  CA2AEX::CA2AEX

Конструктор.

```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*psz*<br/>
Текстовая строка для преобразования.

*nCodePage*<br/>
Не используется в этом классе.

### <a name="remarks"></a>Примечания

Создает буфер, необходимый для перевода.

##  <a name="dtor"></a>  CA2AEX:: ~ CA2AEX

Деструктор

```
~CA2AEX() throw();
```

### <a name="remarks"></a>Примечания

Освобождает выделенный буфер.

##  <a name="m_psz"></a>  CA2AEX::m_psz

Элемент данных, который хранит исходную строку.

```
LPSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CA2AEX::m_szBuffer

Статический буфер, используемый для хранения преобразованную строку.

```
char m_szBuffer[ t_nBufferLength];
```

##  <a name="operator_lpstr"></a>  CA2AEX::operator LPSTR

Оператор преобразования.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текстовую строку, как тип LPSTR.

## <a name="see-also"></a>См. также

[Класс CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Класс CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Класс CW2AEX](../../atl/reference/cw2aex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
