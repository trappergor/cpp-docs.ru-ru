---
title: "Класс freelist | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
dev_langs:
- C++
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 7e4e636045d91cfaa4bc9532344cf73e68cec911
ms.contentlocale: ru-ru
ms.lasthandoff: 10/03/2017

---
# <a name="freelist-class"></a>Класс freelist
Управляет списком блоков памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <std::size_t Sz, class Max>  
class freelist
 : public Max
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Sz`|Число элементов в массиве, которые нужно выделить.|  
|`Max`|Класс max, представляющий максимальное количество элементов, которые необходимо сохранить в свободном списке. Классом max может быть [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) или [max_variable_size](../standard-library/max-variable-size-class.md).|  
  
## <a name="remarks"></a>Примечания  
 Этот класс шаблона управляет списком блоков памяти размером `Sz` с максимальной длиной списка, которая определяется классом max, переданным в `Max`.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[freelist](#freelist)|Создает объект типа `freelist`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[pop](#pop)|Удаляет первый блок памяти из свободного списка.|  
|[push](#push)|Добавляет блок памяти в список.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<allocators>  
  
 **Пространство имен:** stdext  
  
##  <a name="freelist"></a>  freelist::freelist  
 Создает объект типа `freelist`.  
  
```
freelist();
```  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="pop"></a>  freelist::pop  
 Удаляет первый блок памяти из свободного списка.  
  
```
void *pop();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на блок памяти, удаленный из списка.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает `NULL`, если список пуст. В противном случае удаляет первый блок памяти из списка.  
  
##  <a name="push"></a>  freelist::push  
 Добавляет блок памяти в список.  
  
```
bool push(void* ptr);
```  
  
### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`ptr`|Указатель на блок памяти, которые необходимо добавить в свободный список.|  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`, если функция `full` класса max возвращает `false`; в противном случае функция `push` возвращает `false`.  
  
### <a name="remarks"></a>Примечания  
 Если функция `full` класса max возвращает `false`, эта функция-член добавляет блок памяти, на который указывает `ptr`, в начало списка.  
  
## <a name="see-also"></a>См. также  
 [\<allocators>](../standard-library/allocators-header.md)




