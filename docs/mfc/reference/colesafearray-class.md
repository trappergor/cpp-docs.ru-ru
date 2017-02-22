---
title: "COleSafeArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleSafeArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], safe"
  - "COleSafeArray class"
  - "ODBC, safe arrays"
  - "safe arrays"
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleSafeArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс для работы с массивами произвольных типов и измерения.  
  
## Синтаксис  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleSafeArray::COleSafeArray](../Topic/COleSafeArray::COleSafeArray.md)|Создает объект `COleSafeArray`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleSafeArray::AccessData](../Topic/COleSafeArray::AccessData.md)|Извлекает указатель на данные массива.|  
|[COleSafeArray::AllocData](../Topic/COleSafeArray::AllocData.md)|Выделяет память для массива.|  
|[COleSafeArray::AllocDescriptor](../Topic/COleSafeArray::AllocDescriptor.md)|Выделяет память для безопасного дескриптора массива.|  
|[COleSafeArray::Attach](../Topic/COleSafeArray::Attach.md)|Предоставляет элемент управления существующего массива **VARIANT** к объекту `COleSafeArray`.|  
|[COleSafeArray::Clear](../Topic/COleSafeArray::Clear.md)|Освобождает все данные в основном **VARIANT**.|  
|[COleSafeArray::Copy](../Topic/COleSafeArray::Copy.md)|Создает копию существующего массива.|  
|[COleSafeArray::Create](../Topic/COleSafeArray::Create.md)|Создает безопасный массив.|  
|[COleSafeArray::CreateOneDim](../Topic/COleSafeArray::CreateOneDim.md)|Создает одномерный объект `COleSafeArray`.|  
|[COleSafeArray::Destroy](../Topic/COleSafeArray::Destroy.md)|Удаляет существующий массив.|  
|[COleSafeArray::DestroyData](../Topic/COleSafeArray::DestroyData.md)|Удаляет данные в безопасном массиве.|  
|[COleSafeArray::DestroyDescriptor](../Topic/COleSafeArray::DestroyDescriptor.md)|Уничтожает дескриптор безопасного массива.|  
|[COleSafeArray::Detach](../Topic/COleSafeArray::Detach.md)|Наконец удаляет массив **VARIANT** из объекта `COleSafeArray` \(так как не будут освобождены данные\).|  
|[COleSafeArray::GetByteArray](../Topic/COleSafeArray::GetByteArray.md)|Копирует содержимое безопасного массива в [CByteArray](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](../Topic/COleSafeArray::GetDim.md)|Возвращает количество измерений в массиве.|  
|[COleSafeArray::GetElement](../Topic/COleSafeArray::GetElement.md)|Возвращает единственный элемент защищенного массива.|  
|[COleSafeArray::GetElemSize](../Topic/COleSafeArray::GetElemSize.md)|Возвращает размер \(в байтах\) одного элемента в безопасном массиве.|  
|[COleSafeArray::GetLBound](../Topic/COleSafeArray::GetLBound.md)|Возвращает нижнюю границу для любого измерения безопасного массива.|  
|[COleSafeArray::GetOneDimSize](../Topic/COleSafeArray::GetOneDimSize.md)|Возвращает количество элементов одномерного массива объекта `COleSafeArray`.|  
|[COleSafeArray::GetUBound](../Topic/COleSafeArray::GetUBound.md)|Возвращает границы для всех измерений массива безопасного.|  
|[COleSafeArray::Lock](../Topic/COleSafeArray::Lock.md)|Увеличивает число блокировок массива и устанавливает указатель на данные массива в дескрипторе массива.|  
|[COleSafeArray::PtrOfIndex](../Topic/COleSafeArray::PtrOfIndex.md)|Возвращает указатель к индексированному элементу.|  
|[COleSafeArray::PutElement](../Topic/COleSafeArray::PutElement.md)|Присвоит один элемент в массиве.|  
|[COleSafeArray::Redim](../Topic/COleSafeArray::Redim.md)|Изменяет наименее значительные \(крайний справа\) границы безопасного массива.|  
|[COleSafeArray::ResizeOneDim](../Topic/COleSafeArray::ResizeOneDim.md)|Изменяет количество элементов одномерного массива объекта `COleSafeArray`.|  
|[COleSafeArray::UnaccessData](../Topic/COleSafeArray::UnaccessData.md)|Уменьшает количество блокировок массива и объявляет указатель, полученную `AccessData`.|  
|[COleSafeArray::Unlock](../Topic/COleSafeArray::Unlock.md)|Уменьшает количество блокировок массива, поэтому его можно освободить или размера.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleSafeArray::operator LPCVARIANT](../Topic/COleSafeArray::operator%20LPCVARIANT.md)|Обращается к **VARIANT** базовая структура объекта `COleSafeArray`.|  
|[COleSafeArray::operator LPVARIANT](../Topic/COleSafeArray::operator%20LPVARIANT.md)|Обращается к **VARIANT** базовая структура объекта `COleSafeArray`.|  
|[COleSafeArray::operator \=](../Topic/COleSafeArray::operator%20=.md)|Значения копий в объект `COleSafeArray` \(**SAFEARRAY**, **VARIANT**, `COleVariant` или массив `COleSafeArray` \).|  
|[COleSafeArray::operator \=\=](../Topic/COleSafeArray::operator%20==.md)|Сравнивает 2 различных массива \(**SAFEARRAY**, **VARIANT**, `COleVariant` или массивы `COleSafeArray` \).|  
|[COleSafeArray::operator \<\<](../Topic/COleSafeArray::operator%20%3C%3C.md)|Выводит содержимое объекта `COleSafeArray` на контекст дампа.|  
  
## Заметки  
 `COleSafeArray` OLE производным от структуры **VARIANT**.  Функции\-члены OLE **SAFEARRAY** доступны через `COleSafeArray`, а также функции\-члены набор в частности, предназначенных для одномерных массивов байтов.  
  
## Иерархия наследования  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## Требования  
 **Header:**  afxdisp.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../Topic/CRecordset%20Class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)