---
title: "Класс CW2AEX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2AEX
- ATLCONV/ATL::CW2AEX
- ATLCONV/ATL::CW2AEX::CW2AEX
- ATLCONV/ATL::CW2AEX::m_psz
- ATLCONV/ATL::CW2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CW2AEX class
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 007dc4a40f0784984981c9b2741ec79ce6f12d9b
ms.lasthandoff: 03/31/2017

---
# <a name="cw2aex-class"></a>Класс CW2AEX
Этот класс используется макросы преобразования строк `CT2AEX`, `CW2TEX`, `CW2CTEX`, и `CT2CAEX`и определение типа **CW2A**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<int t_nBufferLength = 128>  
class CW2AEX
```  
  
#### <a name="parameters"></a>Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода. Длина по умолчанию — 128 байт.  
  
## <a name="members"></a>Члены  
  
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
 Если не требуется дополнительных функциональных возможностей, используйте `CT2AEX`, `CW2TEX`, `CW2CTEX`, `CT2CAEX`, или **CW2A** в коде.  
  
 Этот класс содержит статические буфера фиксированного размера, который используется для хранения результата преобразования. Если результат слишком большой для помещения в статический буфер, класс выделяет память с помощью `malloc`, освобождая ее, когда объект выходит за пределы области. Это гарантирует, что, в отличие от текста макросы преобразования доступны в предыдущих версиях библиотеки ATL, этот класс можно безопасно использовать в циклах, и что он не будет переполнению стека.  
  
 Если класс пытается выделить память для кучи и завершается с ошибкой, он будет вызывать `AtlThrow` с аргументом **E_OUTOFMEMORY**.  
  
 По умолчанию ATL классы и макросы преобразования используют кодовую страницу ANSI текущего потока для преобразования. Если вы хотите переопределить такой режим работы для определенного преобразования, укажите кодовую страницу в качестве второго параметра конструктора для класса.  
  
 Следующие макросы, основаны на этот класс.  
  
- `CT2AEX`  
  
- `CW2TEX`  
  
- `CW2CTEX`  
  
- `CT2CAEX`  
  
 Следующие typedef зависит от этого класса:  
  
- **CW2A**  
  
 Описание этих макросов текстового преобразования см. в разделе [ATL и MFC макросы преобразования строк](string-conversion-macros.md).  
  
## <a name="example"></a>Пример  
 В разделе [ATL и MFC макросы преобразования строк](string-conversion-macros.md) пример использования эти макросы преобразования строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlconv.h  
  
##  <a name="cw2aex"></a>CW2AEX::CW2AEX  
 Конструктор.  
  
```
CW2AEX(LPCWSTR psz, UINT nCodePage) throw(...);  
CW2AEX(LPCWSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Текстовая строка для преобразования.  
  
 `nCodePage`  
 Кодовая страница, используемая для выполнения преобразования. В описании кода страницы параметров для [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] функция [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072) для получения дополнительных сведений.  
  
### <a name="remarks"></a>Примечания  
 Выделяет буфера, используемого в процессе перевода.  
  
##  <a name="dtor"></a>CW2AEX:: ~ CW2AEX  
 Деструктор  
  
```
~CW2AEX() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенный буфер.  
  
##  <a name="m_psz"></a>CW2AEX::m_psz  
 Элемент данных, который хранит исходную строку.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CW2AEX::m_szBuffer  
 Статический буфер, используемый для хранения преобразованную строку.  
  
```
char m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>CW2AEX::operator LPSTR  
 Оператор преобразования.  
  
```  
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текстовую строку в качестве типа **LPSTR.**  
  
## <a name="see-also"></a>См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

