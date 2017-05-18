---
title: "Класс CFixedStringT | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 17
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f357a70a728b388c3b5d3d26ac4efd0d4c84434a
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cfixedstringt-class"></a>Класс CFixedStringT
Этот класс представляет объект строки с фиксированной символьный буфер.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>Параметры  
 `StringType`  
 Используется в качестве базового класса для объекта фиксированной строки и может быть любой `CStringT`-тип, основанный на. Некоторые примеры `CString`, `CStringA`, и `CStringW`.  
  
 *t_nChars*  
 Число символов, сохраненных в буфере.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|Конструктор для объекта string.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|Присваивает новое значение для `CFixedStringT` объекта.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является примером класса пользовательской строки на основе `CStringT`. Хотя очень похожа, два класса отличаются в реализации. Основные различия между `CFixedStringT` и `CStringT` являются:  
  
-   Буфер начальный символ выделяется в рамках объекта и имеет размер *t_nChars*. Это позволяет **CFixedString** объекта будут занимать блока непрерывной памяти для повышения производительности. Однако если содержимое `CFixedStringT` объект выходит за *t_nChars*, динамическое выделение памяти буфера.  
  
-   Буфер символов для `CFixedStringT` объекта всегда имеют одинаковую длину ( *t_nChars*). Нет ограничений на размер буфера для `CStringT` объектов.  
  
-   Диспетчер памяти для `CFixedStringT` настраивается таким образом, что совместное использование [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) объекта между двумя или более `CFixedStringT` objectsis не допускается. `CStringT`объекты не имеют этого ограничения.  
  
 Дополнительные сведения о настройке `CFixedStringT` и управление памятью для строковых объектов, в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** cstringt.h  
  
##  <a name="cfixedstringt"></a>CFixedStringT::CFixedStringT  
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
 Завершающим нулем строку необходимо скопировать в это `CFixedStringT` объекта.  
  
 `str`  
 Существующий `CFixedStringT` объекта должно быть скопировано в это `CFixedStringT` объекта.  
  
 `pStringMgr`  
 Указатель на диспетчер памяти `CFixedStringT` объекта. Дополнительные сведения о `IAtlStringMgr` и управление памятью для `CFixedStringT`, в разделе [управление памятью и CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
### <a name="remarks"></a>Примечания  
 Поскольку конструкторы скопировать входных данных в новое хранилище, выделенное, следует иметь в виду памяти может привести к исключения. Обратите внимание, что некоторые из этих конструкторов выступать в качестве функции преобразования.  
  
##  <a name="operator__eq"></a>CFixedStringT::operator =  
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
 Завершающим нулем строку необходимо скопировать в это `CFixedStringT` объекта.  
  
 `psz`  
 Существующий `CFixedStringT` необходимо скопировать в это `CFixedStringT` объекта.  
  
### <a name="remarks"></a>Примечания  
 Следует иметь в виду, памяти, исключения могут возникать при использовании оператор присваивания, так как часто выделяется новая память для хранения результирующего `CFixedStringT` объекта.  
  
## <a name="see-also"></a>См. также  
 [Класс CStringT](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы общих библиотек ATL и MFC](../../atl-mfc-shared/atl-mfc-shared-classes.md)





