---
title: "Класс IAccessorImpl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IAccessorImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAccessorImpl - класс"
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс IAccessorImpl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет реализацию интерфейса [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx).  
  
## Синтаксис  
  
```  
template <  
   class T,   
   class BindType = ATLBINDINGS,   
   class BindingVector = CAtlMap <   
      HACCESSOR hAccessor,   
      BindType* pBindingsStructure   
   >   
>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### Параметры  
 `T`  
 Класс набора строк или объекта команд.  
  
 `BindType`  
 Блок памяти для привязки данных.  По умолчанию структура **ATLBINDINGS** \(см. atldb.h\).  
  
 `BindingVector`  
 Блок памяти для информации о столбцах.  По умолчанию [CAtlMap](../../atl/reference/catlmap-class.md) представляет положение, где значение **HACCESSOR** и значения элемента указатель на структуру `BindType`.  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|Конструктор.|  
  
### Методы Interface  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|Добавляет счетчик ссылок в существующий метод доступа.|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|Создает метод доступа из набора привязок.|  
|[GetBindings](../Topic/IAccessorImpl::GetBindings.md)|Возвращает привязки из метода доступа.|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|Освобождает метод доступа.|  
  
## Заметки  
 Это необходимо в наборах строк и командах.  OLE DB требует поставщики реализуют тег **HACCESSOR**, который в массив структур [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  **HACCESSOR** s, `IAccessorImpl` адреса структур `BindType`.  По умолчанию `BindType` определяется в качестве **ATLBINDINGS** в определении шаблона `IAccessorImpl`.  `BindType` предоставляет механизм, используемый `IAccessorImpl` для отслеживания число элементов в массиве его **DBBINDING**, так и число ссылок и флажки доступа.  
  
## Требования  
 **Header:**  atldb.h  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)