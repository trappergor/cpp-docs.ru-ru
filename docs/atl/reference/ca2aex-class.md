---
title: "Класс CA2AEX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CA2AEX<t_nBufferLength>
- CA2AEX
- ATL.CA2AEX<t_nBufferLength>
- ATLCONV/CA2AEX
- ATL.CA2AEX
- ATL::CA2AEX
dev_langs:
- C++
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
caps.latest.revision: 20
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 65637b63cf23d2e7433b575e95d3f53a53ed76a1
ms.lasthandoff: 02/24/2017

---
# <a name="ca2aex-class"></a>Класс CA2AEX
Этот класс используется макросы преобразования строк `CA2TEX` и `CT2AEX`и typedef **CA2A**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <int t_nBufferLength = 128>
class CA2AEX
```  
  
#### <a name="parameters"></a>Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода. Длина по умолчанию равна 128 байт.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2AEX::CA2AEX](#ca2aex)|Конструктор.|  
|[CA2AEX:: ~ CA2AEX](#dtor)|Деструктор|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2AEX::operator LPSTR](#operator_lpstr)|Оператор преобразования.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2AEX::m_psz](#m_psz)|Член данных, хранит исходную строку.|  
|[CA2AEX::m_szBuffer](#m_szbuffer)|Статический буфер, используемый для хранения Преобразованная строка.|  
  
## <a name="remarks"></a>Примечания  
 Если дополнительные функциональные возможности не требуется, используйте `CA2TEX`, `CT2AEX`, или **CA2A** в собственном коде.  
  
 Этот класс содержит статический буфер фиксированного размера, который используется для хранения результата преобразования. Если результат слишком большой для помещения в статический буфер, класс выделяет память с помощью `malloc`, освобождая ее, когда объект выходит за пределы области. Это гарантирует, что, в отличие от текста макросы преобразования, доступных в предыдущих версиях библиотеки ATL, этот класс можно безопасно использовать в циклах, и что он не приводят к переполнению стека.  
  
 Если класс пытается выделить память для кучи и завершается неудачей, он будет вызывать `AtlThrow` с аргументом **E_OUTOFMEMORY**.  
  
 По умолчанию ATL классы и макросы преобразования используют кодовую страницу ANSI текущего потока для преобразования.  
  
 Следующие макросы, основаны на этот класс.  
  
- `CA2TEX`  
  
- `CT2AEX`  
  
 Следующие typedef зависит от этого класса:  
  
- **CA2A**  
  
 Обсуждение этих макросов текстового преобразования см. в разделе [ATL и MFC макросы преобразования строк](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Пример  
 В разделе [ATL и MFC макросы преобразования строк](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) пример использования эти макросы преобразования строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlconv.h  
  
##  <a name="a-nameca2aexa--ca2aexca2aex"></a><a name="ca2aex"></a>CA2AEX::CA2AEX  
 Конструктор.  
  
```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Текстовая строка для преобразования.  
  
 `nCodePage`  
 Не используется в этом классе.  
  
### <a name="remarks"></a>Примечания  
 Создает буфер, необходимый для перевода.  
  
##  <a name="a-namedtora--ca2aexca2aex"></a><a name="dtor"></a>CA2AEX:: ~ CA2AEX  
 Деструктор  
  
```
~CA2AEX() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенный буфер.  
  
##  <a name="a-namempsza--ca2aexmpsz"></a><a name="m_psz"></a>CA2AEX::m_psz  
 Член данных, хранит исходную строку.  
  
```
LPSTR m_psz;
```  
  
##  <a name="a-namemszbuffera--ca2aexmszbuffer"></a><a name="m_szbuffer"></a>CA2AEX::m_szBuffer  
 Статический буфер, используемый для хранения Преобразованная строка.  
  
```
char m_szBuffer[ t_nBufferLength];
```  
  
##  <a name="a-nameoperatorlpstra--ca2aexoperator-lpstr"></a><a name="operator_lpstr"></a>CA2AEX::operator LPSTR  
 Оператор преобразования.  
  
```
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текстовую строку в качестве типа **LPSTR**.  
  
## <a name="see-also"></a>См. также  
 [Класс CA2CAEX](../../atl/reference/ca2caex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
