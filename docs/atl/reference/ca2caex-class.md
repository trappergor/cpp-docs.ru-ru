---
title: "Класс CA2CAEX | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CA2CAEX
- ATL.CA2CAEX<t_nBufferLength>
- ATLCONV/CA2CAEX
- ATL::CA2CAEX<t_nBufferLength>
- ATL::CA2CAEX
- CA2CAEX
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
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
ms.openlocfilehash: f104a62144e7fd8ac802c27dfe940a7f96d0e79a
ms.lasthandoff: 02/24/2017

---
# <a name="ca2caex-class"></a>Класс CA2CAEX
Этот класс используется макросы преобразования строк `CA2CTEX` и `CT2CAEX`и typedef **CA2CA**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода. Длина по умолчанию равна 128 байт.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2CAEX::CA2CAEX](#ca2caex)|Конструктор.|  
|[CA2CAEX:: ~ CA2CAEX](#dtor)|Деструктор|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2CAEX::operator LPCSTR](#operator_lpcstr)|Оператор преобразования.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CA2CAEX::m_psz](#m_psz)|Член данных, хранит исходную строку.|  
  
## <a name="remarks"></a>Примечания  
 Если дополнительные функциональные возможности не требуется, используйте `CA2CTEX`, `CT2CAEX`, или **CA2CA** в собственном коде.  
  
 Этот класс можно безопасно использовать в циклах и не приводят к переполнению стека. По умолчанию классы и макросы преобразования ATL используют для преобразования кодовую страницу ANSI текущего потока.  
  
 Следующие макросы, основаны на этот класс.  
  
- `CA2CTEX`  
  
- `CT2CAEX`  
  
 Следующие typedef зависит от этого класса:  
  
- **CA2CA**  
  
 Обсуждение этих макросов текстового преобразования см. в разделе [ATL и MFC макросы преобразования строк](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863).  
  
## <a name="example"></a>Пример  
 В разделе [ATL и MFC макросы преобразования строк](http://msdn.microsoft.com/library/8f53659e-0464-4424-97db-6b8453c49863) пример использования эти макросы преобразования строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlconv.h  
  
##  <a name="a-nameca2caexa--ca2caexca2caex"></a><a name="ca2caex"></a>CA2CAEX::CA2CAEX  
 Конструктор.  
  
```
CA2CAEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2CAEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Текстовая строка для преобразования.  
  
 `nCodePage`  
 Не используется в этом классе.  
  
### <a name="remarks"></a>Примечания  
 Создает буфер, необходимый для перевода.  
  
##  <a name="a-namedtora--ca2caexca2caex"></a><a name="dtor"></a>CA2CAEX:: ~ CA2CAEX  
 Деструктор  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенный буфер.  
  
##  <a name="a-namempsza--ca2caexmpsz"></a><a name="m_psz"></a>CA2CAEX::m_psz  
 Член данных, хранит исходную строку.  
  
```
LPCSTR m_psz;
```  
  
##  <a name="a-nameoperatorlpcstra--ca2caexoperator-lpcstr"></a><a name="operator_lpcstr"></a>CA2CAEX::operator LPCSTR  
 Оператор преобразования.  
  
```  
operator LPCSTR() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает текстовую строку в качестве типа `LPCSTR`.  
  
## <a name="see-also"></a>См. также  
 [Класс CA2AEX](../../atl/reference/ca2aex-class.md)   
 [Класс CA2WEX](../../atl/reference/ca2wex-class.md)   
 [Класс CW2AEX](../../atl/reference/cw2aex-class.md)   
 [Класс CW2CWEX](../../atl/reference/cw2cwex-class.md)   
 [Класс CW2WEX](../../atl/reference/cw2wex-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

