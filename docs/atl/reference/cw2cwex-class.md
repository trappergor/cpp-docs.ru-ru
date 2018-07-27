---
title: Класс CW2CWEX | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2CWEX
- ATLCONV/ATL::CW2CWEX
- ATLCONV/ATL::CW2CWEX::CW2CWEX
- ATLCONV/ATL::CW2CWEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CW2CWEX class
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f97ddd87194d9cf7cce0b5fcd898b6a9f391d908
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879385"
---
# <a name="cw2cwex-class"></a>Класс CW2CWEX
Этот класс используется, макросы преобразования строк CW2CTEX CT2CWEX и typedef CW2W.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<int t_nBufferLength = 128>  
class CW2CWEX
```  
  
#### <a name="parameters"></a>Параметры  
 *t_nBufferLength*  
 Размер буфера, используемого в процессе перевода. Длина по умолчанию равен 128 байтам.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](#cw2cwex)|Конструктор.|  
|[CW2CWEX:: ~ CW2CWEX](#dtor)|Деструктор|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CW2CWEX::operator LPCWSTR](#operator_lpcwstr)|Оператор преобразования.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CW2CWEX::m_psz](#m_psz)|Элемент данных, который хранит исходную строку.|  
  
## <a name="remarks"></a>Примечания  
 Если дополнительные функциональные возможности не требуется, используйте CW2CTEX, CT2CWEX или CW2W в коде.  
  
 Этот класс можно безопасно использовать в циклах и не приводят к переполнению стека. По умолчанию ATL классы и макросы преобразования используют кодовую страницу ANSI текущего потока для преобразования.  
  
 Следующие макросы основаны на этот класс:  
  
- CW2CTEX  
  
- CT2CWEX  
  
 Следующие определения типа зависит от этого класса:  
  
- CW2W  
  
 Описание этих макросов текстового преобразования, см. в разделе [ATL и макросов преобразования MFC из строки](string-conversion-macros.md).  
  
## <a name="example"></a>Пример  
 См. в разделе [ATL и макросы преобразования строк MFC](string-conversion-macros.md) пример использования эти макросы преобразования строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlconv.h  
  
##  <a name="cw2cwex"></a>  CW2CWEX::CW2CWEX  
 Конструктор.  
  
```
CW2CWEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2CWEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *psz*  
 Текстовая строка для преобразования.  
  
 *nCodePage*  
 Кодовая страница. В этот класс не используется.  
  
### <a name="remarks"></a>Примечания  
 Выделяет буфера, используемого в процессе перевода.  
  
##  <a name="dtor"></a>  CW2CWEX:: ~ CW2CWEX  
 Деструктор  
  
```
~CW2CWEX() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенный буфер.  
  
##  <a name="m_psz"></a>  CW2CWEX::m_psz  
 Элемент данных, который хранит исходную строку.  
  
```
LPCWSTR m_psz;
```  
  
##  <a name="operator_lpcwstr"></a>  CW2CWEX::operator LPCWSTR  
 Оператор преобразования.  
  
```  
operator LPCWSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текстовую строку, при вводе LPCWSTR.  
  
## <a name="see-also"></a>См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
