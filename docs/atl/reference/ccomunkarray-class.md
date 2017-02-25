---
title: "CComUnkArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComUnkArray"
  - "ATL.CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray<nMaxSize>"
  - "ATL::CComUnkArray"
  - "CComUnkArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComUnkArray class"
  - "точки подключения [C++], управление"
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CComUnkArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предназначен для хранения указателей **IUnknown** и предназначен для использования в качестве параметра [IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md) к классу шаблона.  
  
## Синтаксис  
  
```  
template<  
   unsigned int nMaxSize  
>  
class CComUnkArray  
```  
  
#### Параметры  
 *nMaxSize*  
 Максимальное число указателей **IUnknown**, которые могут храниться в статическом массиве.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComUnkArray::CComUnkArray](../Topic/CComUnkArray::CComUnkArray.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComUnkArray::Add](../Topic/CComUnkArray::Add.md)|Вызовите этот метод, чтобы добавить указатель **IUnknown** в массив.|  
|[CComUnkArray::begin](../Topic/CComUnkArray::begin.md)|Возвращает указатель на первый указателю **IUnknown** в коллекции.|  
|[CComUnkArray::end](../Topic/CComUnkArray::end.md)|Возвращает указатель на одно за последним указателем **IUnknown** в коллекции.|  
|[CComUnkArray::GetCookie](../Topic/CComUnkArray::GetCookie.md)|Вызовите этот метод, чтобы получить файл cookie, связанный с заданным указателем **IUnknown**.|  
|[CComUnkArray::GetUnknown](../Topic/CComUnkArray::GetUnknown.md)|Вызовите этот метод, чтобы получить указатель **IUnknown**, связанный с данным файлом cookie.|  
|[CComUnkArray::Remove](../Topic/CComUnkArray::Remove.md)|Вызовите этот метод, чтобы удалить указатель **IUnknown** из массива.|  
  
## Заметки  
 **CComUnkArray** содержит фиксированное число указателей, каждый из **IUnknown** интерфейс в точке подключения.  **CComUnkArray** может использоваться в качестве параметра к классу шаблона [IConnectionPointImpl](../Topic/IConnectionPointImpl%20Class.md).  **CComUnkArray\<1\>** специализация шаблона **CComUnkArray**, которая была оптимизирована для одной точки подключения.  
  
 Методы [begin](../Topic/CComUnkArray::begin.md) и [конец](../Topic/CComUnkArray::end.md)**CComUnkArray** можно использовать для организация цикла через все точки подключения \(например, при инициировано событие\).  
  
 Дополнительные сведения см. в разделе [Adding Connection Points to an Object](../../atl/adding-connection-points-to-an-object.md) на автоматизировать создание прокси\-объектов точки подключения.  
  
> [!NOTE]
>  **Примечание** Класс используется [CComDynamicUnkArray](../Topic/CComDynamicUnkArray%20Class.md) мастером **Добавление класса** создать элемент управления, имеющий точки подключения.  Если необходимо определить количество точек соединения вручную, измените ссылку из **CComDynamicUnkArray** к `CComUnkArray<` *n* , где *n* \- количество `>` требуется точек подключения.  
  
## Требования  
 **Header:**  atlcom.h  
  
## См. также  
 [CComDynamicUnkArray Class](../Topic/CComDynamicUnkArray%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)