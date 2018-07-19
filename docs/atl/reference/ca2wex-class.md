---
title: Класс CA2WEX | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2WEX
- ATLCONV/ATL::CA2WEX
- ATLCONV/ATL::CA2WEX::CA2WEX
- ATLCONV/ATL::CA2WEX::m_psz
- ATLCONV/ATL::CA2WEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2WEX class
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f19046cc825fabd2a3a41020a9f4c141dc98489e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882823"
---
# <a name="ca2wex-class"></a>Класс CA2WEX
Этот класс используется, макросы преобразования строк CA2TEX, CA2CTEX, CT2WEX и CT2CWEX и typedef CA2W.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <int t_nBufferLength = 128>
class CA2WEX
```  
  
#### <a name="parameters"></a>Параметры  
 *t_nBufferLength*  
 Размер буфера, используемого в процессе перевода. Длина по умолчанию равен 128 байтам.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CA2WEX::CA2WEX](#ca2wex)|Конструктор.|  
|[CA2WEX:: ~ CA2WEX](#dtor)|Деструктор|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CA2WEX::operator LPWSTR](#operator_lpwstr)|Оператор преобразования.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CA2WEX::m_psz](#m_psz)|Элемент данных, который хранит исходную строку.|  
|[CA2WEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованную строку.|  
  
## <a name="remarks"></a>Примечания  
 Если дополнительные функциональные возможности не требуется, используйте CA2TEX, CA2CTEX, CT2WEX, CT2CWEX или CA2W в коде.  
  
 Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком велик для помещения в статический буфер, класс выделяет память с помощью **malloc**, освободить память, когда объект выходит за пределы области действия. Это гарантирует, что, в отличие от текста макросы преобразования, доступных в предыдущих версиях библиотеки ATL, этот класс можно безопасно использовать в циклах, и что он не приводят к переполнению стека.  
  
 Если класс пытается выделить память для кучи и происходит сбой, он вызывает `AtlThrow` с аргументом E_OUTOFMEMORY.  
  
 По умолчанию ATL классы и макросы преобразования используют кодовую страницу ANSI текущего потока для преобразования. Если вы хотите переопределить это поведение для определенного преобразования, укажите кодовую страницу в качестве второго параметра в конструктор для класса.  
  
 Следующие макросы основаны на этот класс:  
  
- CA2TEX  
  
- CA2CTEX  
  
- CT2WEX  
  
- CT2CWEX  
  
 Следующие определения типа зависит от этого класса:  
  
- CA2W  
  
 Описание этих макросов текстового преобразования, см. в разделе [ATL и макросов преобразования MFC из строки](string-conversion-macros.md).  
  
## <a name="example"></a>Пример  
 См. в разделе [ATL и макросы преобразования строк MFC](string-conversion-macros.md) пример использования эти макросы преобразования строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlconv.h  
  
##  <a name="ca2wex"></a>  CA2WEX::CA2WEX  
 Конструктор.  
  
```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 *psz*  
 Текстовая строка для преобразования.  
  
 *nCodePage*  
 Кодовую страницу, используемую для выполнения преобразования. См. в обсуждении параметр кода страницы для функции Windows SDK [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) для получения дополнительных сведений.  
  
### <a name="remarks"></a>Примечания  
 Выделяет буфера, используемого в процессе перевода.  
  
##  <a name="dtor"></a>  CA2WEX:: ~ CA2WEX  
 Деструктор  
  
```
~CA2WEX() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенный буфер.  
  
##  <a name="m_psz"></a>  CA2WEX::m_psz  
 Элемент данных, который хранит исходную строку.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CA2WEX::m_szBuffer  
 Статический буфер, используемый для хранения преобразованную строку.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>  CA2WEX::operator LPWSTR  
 Оператор преобразования.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текстовую строку, при вводе LPWSTR.  
  
## <a name="see-also"></a>См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
