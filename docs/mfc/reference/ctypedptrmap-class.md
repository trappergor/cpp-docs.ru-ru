---
title: CTypedPtrMap-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdb0c8679990a48740032017a2c0e11b7148f2d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33376399"
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
 Базовый класс для класса map типизированных указателей; должен быть классом карты указатель ( `CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`, или `CMapStringToPtr`).  
  
 `KEY`  
 Класс объекта, который используется как ключ для карты.  
  
 `VALUE`  
 Класс объекта, хранимый в сопоставлении.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|Получает следующий элемент для выполнения итерации.|  
|[CTypedPtrMap::Lookup](#lookup)|Возвращает `KEY` на основе `VALUE`.|  
|[CTypedPtrMap::RemoveKey](#removekey)|Удаляет элемент, указанный с помощью ключа.|  
|[CTypedPtrMap::SetAt](#setat)|Вставляет элемент в сопоставление; заменяет существующий элемент, если найден соответствующий ключ.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[[CTypedPtrMap::operator]](#operator_at)|Вставляет элемент в сопоставление.|  
  
## <a name="remarks"></a>Примечания  
 При использовании `CTypedPtrMap`, средство проверки типов C++ позволяет избежать ошибок, вызванных типы несоответствие указателей.  
  
 Так как все `CTypedPtrMap` функции — это встроенные, использование этого шаблона не влияет на значительно размер или скорость кода.  
  
 Дополнительные сведения об использовании `CTypedPtrMap`, см. в статьях [коллекций](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `BASE_CLASS`  
  
 `CTypedPtrMap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxtempl.h  
  
##  <a name="getnextassoc"></a>  CTypedPtrMap::GetNextAssoc  
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
  
 *KEY*  
 Параметр шаблона, определяющий тип сопоставления ключей.  
  
 `rKey`  
 Указывает возвращаемый ключ полученного элемента.  
  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указывающий тип значений карты.  
  
 `rValue`  
 Указывает возвращаемое значение полученного элемента.  
  
### <a name="remarks"></a>Примечания  
 Эта функция полезна для перебора всех элементов в объекте map. Обратите внимание, что порядковый номер позиции не обязательно будет таким же, как последовательность значение ключа.  
  
 Если полученного элемента является последним в схеме, то новое значение `rNextPosition` равно **NULL**.  
  
 Это встроенная функция вызывает `BASE_CLASS` **:: GetNextAssoc**.  
  
##  <a name="lookup"></a>  CTypedPtrMap::Lookup  
 `Lookup` использует алгоритм хэширования для быстрого поиска элемента карты с ключом, который соответствует в точности.  
  
```  
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Параметры  
 `BASE_CLASS`  
 Параметр шаблона, указывающий на этой карте класса базового класса.  
  
 `key`  
 Ключ элемента, который требуется найти.  
  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указывающий тип значения, хранящиеся в этой схеме.  
  
 `rValue`  
 Указывает возвращаемое значение полученного элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент найден; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Это встроенная функция вызывает `BASE_CLASS` **:: подстановки**.  
  
##  <a name="operator_at"></a>  [CTypedPtrMap::operator]  
 Этот оператор можно использовать только в левой части оператора присваивания (l значение).  
  
```  
VALUE& operator[ ](base_class ::base_arg_key key);
```  
  
### <a name="parameters"></a>Параметры  
 *ЗНАЧЕНИЕ*  
 Параметр шаблона, указывающий тип значения, хранящиеся в этой схеме.  
  
 `BASE_CLASS`  
 Параметр шаблона, указывающий на этой карте класса базового класса.  
  
 `key`  
 Ключ элемента для поиска или создания в схеме.  
  
### <a name="remarks"></a>Примечания  
 Если ни один элемент карты с указанным ключом, создается новый элемент. Нет нет» справа от оператора» (r-значение) эквивалентно этот оператор, так как имеется возможность того, что ключ не может находиться в схеме. Используйте `Lookup` функция-член для извлечения элементов.  
  
##  <a name="removekey"></a>  CTypedPtrMap::RemoveKey  
 Эта функция-член вызывает `BASE_CLASS` **:: RemoveKey**.  
  
```  
BOOL RemoveKey(KEY key);
```  
  
### <a name="parameters"></a>Параметры  
 *KEY*  
 Параметр шаблона, определяющий тип сопоставления ключей.  
  
 `key`  
 Ключ элемента, который требуется удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если элемент был найден и успешно удален. в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey).  
  
##  <a name="setat"></a>  CTypedPtrMap::SetAt  
 Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(KEY key, VALUE newValue);
```  
  
### <a name="parameters"></a>Параметры  
 *KEY*  
 Параметр шаблона, определяющий тип сопоставления ключей.  
  
 `key`  
 Указывает значение ключа новое значение.  
  
 `newValue`  
 Задает указатель на объект, являющийся значением нового элемента.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные примечания см. в разделе [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC СБОРА](../../visual-cpp-samples.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)   
 [Класс CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)   
 [Класс CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)   
 [Класс CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)
