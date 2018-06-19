---
title: Класс CA2CAEX | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2CAEX
- ATLCONV/ATL::CA2CAEX
- ATLCONV/ATL::CA2CAEX::CA2CAEX
- ATLCONV/ATL::CA2CAEX::m_psz
dev_langs:
- C++
helpviewer_keywords:
- CA2CAEX class
ms.assetid: 388e7c1d-a144-474c-a182-b15f69a74bd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8aa16122a1cb3a5f8378397363a45cd28ddaef6d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357806"
---
# <a name="ca2caex-class"></a>Класс CA2CAEX
Этот класс используется макросы преобразования строк `CA2CTEX` и `CT2CAEX`и определение типа **CA2CA**.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<int t_nBufferLength = 128>  
class CA2CAEX
```  
  
#### <a name="parameters"></a>Параметры  
 `t_nBufferLength`  
 Размер буфера, используемого в процессе перевода. Длина по умолчанию — 128 байт.  
  
## <a name="members"></a>Участники  
  
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
|[CA2CAEX::m_psz](#m_psz)|Элемент данных, который хранит исходную строку.|  
  
## <a name="remarks"></a>Примечания  
 Если не требуется дополнительных функциональных возможностей, используйте `CA2CTEX`, `CT2CAEX`, или **CA2CA** в собственном коде.  
  
 Этот класс можно безопасно использовать в циклах и не переполнению стека. По умолчанию классы и макросы преобразования ATL используют для преобразования кодовую страницу ANSI текущего потока.  
  
 Следующие макросы, основаны на этот класс.  
  
- `CA2CTEX`  
  
- `CT2CAEX`  
  
 Следующие typedef зависит от этого класса:  
  
- **CA2CA**  
  
 Описание этих макросов текстового преобразования см. в разделе [ATL и MFC макросы преобразования строк](string-conversion-macros.md).  
  
## <a name="example"></a>Пример  
 В разделе [ATL и MFC макросы преобразования строк](string-conversion-macros.md) пример использования эти макросы преобразования строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlconv.h  
  
##  <a name="ca2caex"></a>  CA2CAEX::CA2CAEX  
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
  
##  <a name="dtor"></a>  CA2CAEX:: ~ CA2CAEX  
 Деструктор  
  
```
~CA2CAEX() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает выделенный буфер.  
  
##  <a name="m_psz"></a>  CA2CAEX::m_psz  
 Элемент данных, который хранит исходную строку.  
  
```
LPCSTR m_psz;
```  
  
##  <a name="operator_lpcstr"></a>  CA2CAEX::operator LPCSTR  
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
