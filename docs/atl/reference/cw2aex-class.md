---
title: Класс CW2AEX
ms.date: 11/04/2016
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
ms.openlocfilehash: 5e9d72ddde6b885343c27ef7cdea44d4d61d20c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50509439"
---
# <a name="cw2aex-class"></a>Класс CW2AEX

Этот класс используется, макросы преобразования строк CT2AEX, CW2TEX, CW2CTEX и CT2CAEX и typedef CW2A.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<int t_nBufferLength = 128>
class CW2AEX
```

#### <a name="parameters"></a>Параметры

*t_nBufferLength*<br/>
Размер буфера, используемого в процессе перевода. Длина по умолчанию равен 128 байтам.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CW2AEX::CW2AEX](#cw2aex)|Конструктор.|
|[CW2AEX:: ~ CW2AEX](#dtor)|Деструктор|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CW2AEX::operator LPSTR](#operator_lpstr)|Оператор преобразования.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CW2AEX::m_psz](#m_psz)|Элемент данных, который хранит исходную строку.|
|[CW2AEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованную строку.|

## <a name="remarks"></a>Примечания

Если дополнительные функциональные возможности не требуется, используйте CT2AEX, CW2TEX, CW2CTEX, CT2CAEX или CW2A в коде.

Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком велик для помещения в статический буфер, класс выделяет память с помощью **malloc**, освободить память, когда объект выходит за пределы области действия. Это гарантирует, что, в отличие от текста макросы преобразования, доступных в предыдущих версиях библиотеки ATL, этот класс можно безопасно использовать в циклах, и что он не приводят к переполнению стека.

Если класс пытается выделить память для кучи и происходит сбой, он вызывает `AtlThrow` с аргументом E_OUTOFMEMORY.

По умолчанию ATL классы и макросы преобразования используют кодовую страницу ANSI текущего потока для преобразования. Если вы хотите переопределить это поведение для определенного преобразования, укажите кодовую страницу в качестве второго параметра в конструктор для класса.

Следующие макросы основаны на этот класс:

- CT2AEX

- CW2TEX

- CW2CTEX

- CT2CAEX

Следующие определения типа зависит от этого класса:

- CW2A

Описание этих макросов текстового преобразования, см. в разделе [ATL и макросов преобразования MFC из строки](string-conversion-macros.md).

## <a name="example"></a>Пример

См. в разделе [ATL и макросы преобразования строк MFC](string-conversion-macros.md) пример использования эти макросы преобразования строк.

## <a name="requirements"></a>Требования

**Заголовок:** atlconv.h

##  <a name="cw2aex"></a>  CW2AEX::CW2AEX

Конструктор.

```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2AEX(LPCWSTR psz) throw(...);
```

### <a name="parameters"></a>Параметры

*psz*<br/>
Текстовая строка для преобразования.

*nCodePage*<br/>
Кодовую страницу, используемую для выполнения преобразования. См. в обсуждении параметр кода страницы для функции Windows SDK [MultiByteToWideChar](/windows/desktop/api/stringapiset/nf-stringapiset-multibytetowidechar) для получения дополнительных сведений.

### <a name="remarks"></a>Примечания

Выделяет буфера, используемого в процессе перевода.

##  <a name="dtor"></a>  CW2AEX:: ~ CW2AEX

Деструктор

```
~CW2AEX() throw();
```

### <a name="remarks"></a>Примечания

Освобождает выделенный буфер.

##  <a name="m_psz"></a>  CW2AEX::m_psz

Элемент данных, который хранит исходную строку.

```
LPSTR m_psz;
```

##  <a name="m_szbuffer"></a>  CW2AEX::m_szBuffer

Статический буфер, используемый для хранения преобразованную строку.

```
char m_szBuffer[t_nBufferLength];
```

##  <a name="operator_lpstr"></a>  CW2AEX::operator LPSTR

Оператор преобразования.

```
operator LPSTR() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает текстовую строку, как тип LPSTR.

## <a name="see-also"></a>См. также

[Класс CA2AEX](../../atl/reference/ca2aex-class.md)<br/>
[Класс CA2CAEX](../../atl/reference/ca2caex-class.md)<br/>
[Класс CA2WEX](../../atl/reference/ca2wex-class.md)<br/>
[Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)<br/>
[Класс CW2WEX](../../atl/reference/cw2wex-class.md)<br/>
[Общие сведения о классе](../../atl/atl-class-overview.md)
