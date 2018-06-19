---
title: Класс CFixedStringT | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93125d15be32a95d71c763f476fad700dab65a3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356991"
---
# <a name="cfixedstringt-class"></a>Класс CFixedStringT
Этот класс представляет строковый объект с буфером символов фиксированной.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>Параметры  
 `StringType`  
 Используется как базовый класс для фиксированной строки объекта и может быть любым `CStringT`-тип, основанный на. Некоторые примеры `CString`, `CStringA`, и `CStringW`.  
  
 *t_nChars*  
 Число символов, сохраненных в буфере.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Конструктор объекта string.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|Присваивает новое значение для `CFixedStringT` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является примером класса настраиваемой строки на основе `CStringT`. Хотя очень похожа два класса отличаются в реализации. Основные различия между `CFixedStringT` и `CStringT` являются:  
  
-   Буфер исходного символа выделяется как часть объекта, а размер *t_nChars*. Это позволяет **CFixedString** объекта занимая блок непрерывной памяти для повышения производительности. Однако если содержимое `CFixedStringT` объект выходит за *t_nChars*, буфер выделяется динамически.  
  
-   Буфер символов для `CFixedStringT` объект всегда имеют одинаковую длину поля ( *t_nChars*). Нет ограничений на размер буфера для `CStringT` объектов.  
  
-   Диспетчер памяти для `CFixedStringT` настраивается таким образом, что общий доступ к [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) объекта между двумя или несколькими `CFixedStringT` objectsis не допускается. `CStringT` объекты не имеют этого ограничения.  
  
 Дополнительные сведения о настройке `CFixedStringT` и управление памятью для строковых объектов см. в общем случае [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** cstringt.h  
  
##  <a name="cfixedstringt"></a>  CFixedStringT::CFixedStringT  
 Создает объект `CFixedStringT`.  
  
```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```  
  
### <a name="parameters"></a>Параметры  
 `psz`  
 Идентифицирующий копируется это `CFixedStringT` объекта.  
  
 `str`  
 Существующий `CFixedStringT` объект копируется это `CFixedStringT` объекта.  
  
 `pStringMgr`  
 Указатель на диспетчер памяти `CFixedStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CFixedStringT`, в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Примечания  
 Поскольку конструкторы копирования входных данных в новое хранилище, выделенное, следует иметь в виду, что память может привести к исключения. Обратите внимание, что некоторые из этих конструкторов действуют как функции преобразования.  
  
##  <a name="operator__eq"></a>  CFixedStringT::operator =  
 Повторно инициализирует существующий `CFixedStringT` объекта с новыми данными.  
  
```
CFixedStringT<StringType, t_nChars>& operator=(
  const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Идентифицирующий копируется это `CFixedStringT` объекта.  
  
 `psz`  
 Существующий `CFixedStringT` необходимо скопировать в это `CFixedStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Следует иметь в виду, памяти, исключения могут возникать при каждом использовании оператор присваивания, так как часто выделяется новая память для хранения результирующего `CFixedStringT` объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [ATL и MFC общие классы](../../atl-mfc-shared/atl-mfc-shared-classes.md)




