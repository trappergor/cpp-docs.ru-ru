---
title: Класс CW2WEX | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e70ba1fdf42ea2f00b057d9b95105b34d9eff5a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="cw2wex-class"></a>Класс CW2WEX
Этот класс используется макросы преобразования строк `CW2TEX` и `CT2WEX`и определение типа `CW2W`.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <int t_nBufferLength = 128>  
class CW2WEX
```  
  
#### <a name="parameters"></a>Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода. Длина по умолчанию — 128 байт.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CW2WEX::CW2WEX](#cw2wex)|Конструктор.|  
|[CW2WEX:: ~ CW2WEX](#dtor)|Деструктор|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CW2WEX::operator LPWSTR](#operator_lpwstr)|Оператор преобразования.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CW2WEX::m_psz](#m_psz)|Элемент данных, который хранит исходную строку.|  
|[CW2WEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованную строку.|  
  
## <a name="remarks"></a>Примечания  
 Если не требуется дополнительных функциональных возможностей, используйте `CW2TEX`, `CT2WEX`, или `CW2W` в коде.  
  
 Этот класс содержит статические буфера фиксированного размера, который используется для хранения результата преобразования. Если результат слишком большой для помещения в статический буфер, класс выделяет память с помощью `malloc`, освобождая ее, когда объект выходит за пределы области. Это гарантирует, что, в отличие от текста макросы преобразования доступны в предыдущих версиях библиотеки ATL, этот класс можно безопасно использовать в циклах, и что он не будет переполнению стека.  
  
 Если класс пытается выделить память для кучи и завершается с ошибкой, он будет вызывать `AtlThrow` с аргументом **E_OUTOFMEMORY**.  
  
 По умолчанию ATL классы и макросы преобразования используют кодовую страницу ANSI текущего потока для преобразования.  
  
 Следующие макросы, основаны на этот класс.  
  
- `CW2TEX`  
  
- `CT2WEX`  
  
 Следующие typedef зависит от этого класса:  
  
- `CW2W`  
  
 Описание этих макросов текстового преобразования см. в разделе [ATL и MFC макросы преобразования строк](string-conversion-macros.md).  
  
## <a name="example"></a>Пример  
 В разделе [ATL и MFC макросы преобразования строк](string-conversion-macros.md) пример использования эти макросы преобразования строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlconv.h  
  
##  <a name="cw2wex"></a>  CW2WEX::CW2WEX  
 Конструктор.  
  
```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Текстовая строка для преобразования.  
  
 `nCodePage`  
 Кодовая страница. Не используется в этом классе.  
  
### <a name="remarks"></a>Примечания  
 Создает буфер, необходимый для перевода.  
  
##  <a name="dtor"></a>  CW2WEX:: ~ CW2WEX  
 Деструктор...  
  
```
~CW2WEX() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенный буфер.  
  
##  <a name="m_psz"></a>  CW2WEX::m_psz  
 Элемент данных, который хранит исходную строку.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CW2WEX::m_szBuffer  
 Статический буфер, используемый для хранения преобразованную строку.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>  CW2WEX::operator LPWSTR  
 Оператор приведения.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текстовую строку в качестве типа `LPWSTR`.  
  
## <a name="see-also"></a>См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
