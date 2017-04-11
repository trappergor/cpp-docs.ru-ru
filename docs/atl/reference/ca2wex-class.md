---
title: "Класс CA2WEX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 93f3fdbd9c728dcaea0262cb774fe5891e6a9838
ms.lasthandoff: 03/31/2017

---
# <a name="ca2wex-class"></a>Класс CA2WEX
Этот класс используется макросы преобразования строк `CA2TEX`, `CA2CTEX`, `CT2WEX`, и `CT2CWEX`и определение типа **CA2W**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <int t_nBufferLength = 128>
class CA2WEX
```  
  
#### <a name="parameters"></a>Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода. Длина по умолчанию — 128 байт.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2WEX::CA2WEX](#ca2wex)|Конструктор.|  
|[CA2WEX:: ~ CA2WEX](#dtor)|Деструктор|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2WEX::operator LPWSTR](#operator_lpwstr)|Оператор преобразования.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2WEX::m_psz](#m_psz)|Элемент данных, который хранит исходную строку.|  
|[CA2WEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения преобразованную строку.|  
  
## <a name="remarks"></a>Примечания  
 Если не требуется дополнительных функциональных возможностей, используйте `CA2TEX`, `CA2CTEX`, `CT2WEX`, `CT2CWEX`, или **CA2W** в коде.  
  
 Этот класс содержит статические буфера фиксированного размера, который используется для хранения результата преобразования. Если результат слишком большой для помещения в статический буфер, класс выделяет память с помощью `malloc`, освобождая ее, когда объект выходит за пределы области. Это гарантирует, что, в отличие от текста макросы преобразования доступны в предыдущих версиях библиотеки ATL, этот класс можно безопасно использовать в циклах, и что он не будет переполнению стека.  
  
 Если класс пытается выделить память для кучи и завершается с ошибкой, он будет вызывать `AtlThrow` с аргументом **E_OUTOFMEMORY**.  
  
 По умолчанию ATL классы и макросы преобразования используют кодовую страницу ANSI текущего потока для преобразования. Если вы хотите переопределить такой режим работы для определенного преобразования, укажите кодовую страницу в качестве второго параметра конструктора для класса.  
  
 Следующие макросы, основаны на этот класс.  
  
- `CA2TEX`  
  
- `CA2CTEX`  
  
- `CT2WEX`  
  
- `CT2CWEX`  
  
 Следующие typedef зависит от этого класса:  
  
- **CA2W**  
  
 Описание этих макросов текстового преобразования см. в разделе [ATL и MFC макросы преобразования строк](string-conversion-macros.md).  
  
## <a name="example"></a>Пример  
 В разделе [ATL и MFC макросы преобразования строк](string-conversion-macros.md) пример использования эти макросы преобразования строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlconv.h  
  
##  <a name="ca2wex"></a>CA2WEX::CA2WEX  
 Конструктор.  
  
```
CA2WEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2WEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Текстовая строка для преобразования.  
  
 `nCodePage`  
 Кодовая страница, используемая для выполнения преобразования. В описании кода страницы параметров для [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] функция [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) для получения дополнительных сведений.  
  
### <a name="remarks"></a>Примечания  
 Выделяет буфера, используемого в процессе перевода.  
  
##  <a name="dtor"></a>CA2WEX:: ~ CA2WEX  
 Деструктор  
  
```
~CA2WEX() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенный буфер.  
  
##  <a name="m_psz"></a>CA2WEX::m_psz  
 Элемент данных, который хранит исходную строку.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CA2WEX::m_szBuffer  
 Статический буфер, используемый для хранения преобразованную строку.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>CA2WEX::operator LPWSTR  
 Оператор преобразования.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текстовую строку в качестве типа **LPWSTR.**  
  
## <a name="see-also"></a>См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

