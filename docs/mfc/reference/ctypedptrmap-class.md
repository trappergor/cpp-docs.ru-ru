---
title: "CTypedPtrMap-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- type-safe collections
- template classes, CTypedPtrMap class
- maps
- CTypedPtrMap class
- pointer maps
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 919d751c6ffe4b10ffad047f1b6be832bf49a1af
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap-класс
Предоставляет типобезопасную "программу-оболочку" для объектов классов карты указателей `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`и `CMapStringToPtr`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class BASE_CLASS, class KEY, class VALUE>  
class CTypedPtrMap : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Базовый класс для класса map типизированный указатель; должен быть классом карты указатель ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, или `CMapStringToPtr`).  
  
 `KEY`  
 Класс объекта, используемого в качестве ключа для сопоставления.  
  
 `VALUE`  
 Класс объекта, хранимый в сопоставлении.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для итерации.|  
|[CTypedPtrMap::Lookup](#lookup)|Возвращает `KEY` на основе `VALUE`.|  
|[CTypedPtrMap::RemoveKey](#removekey)|Удаляет элемент с указанным ключом.|  
|[CTypedPtrMap::SetAt](#setat)|Вставляет элемент в схеме; заменяет существующий элемент, если найден соответствующий ключ.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CTypedPtrMap::operator]](#operator_at)|Вставляет элемент в схеме.|  
  
## <a name="remarks"></a>Примечания  
 При использовании `CTypedPtrMap`, средство проверки типов C++ позволяет избежать ошибок, вызванных указатель несовпадающие типы.  
  
 Так как все `CTypedPtrMap` функций, встроенных, этот шаблон не влияет на значительно размер или скорость кода.  
  
 Дополнительные сведения об использовании `CTypedPtrMap`, см. в статьях [коллекции](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtempl.h  
  
##  <a name="getnextassoc"></a>CTypedPtrMap::GetNextAssoc  
 Извлекает элемент карты по `rNextPosition`, затем обновляет `rNextPosition` для обращения к следующему элементу в схеме.  
  
```  
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `rPosition`  
 Указывает ссылку на **ПОЗИЦИИ** значение, возвращенное предыдущим `GetNextAssoc` или `BASE_CLASS` **:: GetStartPosition** вызова.  
  
 *КЛЮЧ*  
 Параметр шаблона, указав тип сопоставления ключей.  
  
 `rKey`  
 Указывает возвращаемый ключ полученного элемента.  
  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указав тип сопоставления значений.  
  
 `rValue`  
 Указывает возвращаемое значение полученного элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для перебора всех элементов в сопоставлении. Обратите внимание, что порядковый номер позиции не обязательно совпадает с последовательности значение ключа.  
  
 Если полученного элемента является последним в схеме, то новое значение `rNextPosition` равен **NULL**.  
  
 Это встроенная функция вызывает `BASE_CLASS` **:: GetNextAssoc**.  
  
##  <a name="lookup"></a>CTypedPtrMap::Lookup  
 `Lookup`использует алгоритм хэширования для быстрого поиска элемента карты с ключом, который соответствует в точности.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Параметр шаблона, указание базового класса для класса на этой карте.  
  
 `key`  
 Ключ элемента, который требуется найти.  
  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указывающие тип значения, хранящиеся в этой карте.  
  
 `rValue`  
 Указывает возвращаемое значение полученного элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это встроенная функция вызывает `BASE_CLASS` **:: поиска**.  
  
##  <a name="operator_at"></a>[CTypedPtrMap::operator]  
 Этот оператор может использоваться только в левой части оператора присваивания (l значение).  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>Параметры  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указывающие тип значения, хранящиеся в этой карте.  
  
 `BASE_CLASS`  
 Параметр шаблона, указание базового класса для класса на этой карте.  
  
 `key`  
 Ключ элемента для поиска или создания в сопоставлении.  
  
### <a name="remarks"></a>Примечания  
 Если ни один элемент карты с указанным ключом, создается новый элемент. Существует не «справа» (r-значение) эквивалентен этот оператор, так как существует вероятность, что ключ может быть не найдена в схеме. Используйте `Lookup` функции-члена для извлечения элементов.  
  
##  <a name="removekey"></a>CTypedPtrMap::RemoveKey  
 Эта функция-член вызывает `BASE_CLASS` **:: RemoveKey**.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>Параметры  
 *КЛЮЧ*  
 Параметр шаблона, указав тип сопоставления ключей.  
  
 `key`  
 Ключ элемента для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент был найден и успешно удален; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).  
  
##  <a name="setat"></a>CTypedPtrMap::SetAt  
 Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>Параметры  
 *КЛЮЧ*  
 Параметр шаблона, указав тип сопоставления ключей.  
  
 `key`  
 Указывает значение ключа новое значение.  
  
 `newValue`  
 Указывает указателя на объект, являющийся значением нового элемента.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC сбор данных](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)   
 [Класс CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)   
 [Класс CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)   
 [Класс CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)

