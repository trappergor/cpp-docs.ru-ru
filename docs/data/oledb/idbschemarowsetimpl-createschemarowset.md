---
title: "IDBSchemaRowsetImpl::CreateSchemaRowset | Microsoft Docs"
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
  - "IDBSchemaRowsetImpl::CreateSchemaRowset"
  - "ATL::IDBSchemaRowsetImpl::CreateSchemaRowset"
  - "CreateSchemaRowset"
  - "IDBSchemaRowsetImpl.CreateSchemaRowset"
  - "ATL.IDBSchemaRowsetImpl.CreateSchemaRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSchemaRowset - метод"
ms.assetid: ad3e3e4d-45b9-461c-b7b8-3af6843631b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBSchemaRowsetImpl::CreateSchemaRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует функцию создателя COM\-объекта для объекта, указанного параметром шаблона.  
  
## Синтаксис  
  
```  
  
template < class   
SchemaRowsetClass  
 >  
HRESULT CreateSchemaRowset(  
   IUnknown *  
pUnkOuter  
,  
   ULONG   
cRestrictions  
,  
   const VARIANT   
rgRestrictions  
[],  
   REFIID   
riid  
,  
   ULONG   
cPropertySets  
,  
   DBPROPSET   
rgPropertySets  
[],  
   IUnknown**   
ppRowset  
,  
   SchemaRowsetClass*&   
pSchemaRowset  
);  
  
```  
  
#### Параметры  
 `pUnkOuter`  
 \[входные данные\] Внешний [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) при агрегировании; в противном случае — **NULL**.  
  
 `cRestrictions`  
 \[входные данные\] Число ограничений, применяемых к набору строк.  
  
 `rgRestrictions`  
 \[входные данные\] Массив `cRestrictions` **VARIANT**, применяемых к набору строк.  
  
 `riid`  
 \[входные данные\] Интерфейс [QueryInterface](../../atl/queryinterface.md) для выходного значения **IUnknown**.  
  
 `cPropertySets`  
 \[входные данные\] Число задаваемых наборов свойств.  
  
 `rgPropertySets`  
 \[входные данные\] Массив структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), определяющих задаваемые свойства.  
  
 `ppRowset`  
 \[выходные данные\] Выходное значение **IUnknown**, запрошенное `riid`.**IUnknown** — это интерфейс объекта набора строк схемы.  
  
 `pSchemaRowset`  
 \[выходные данные\] Указатель на экземпляр класса набора строк схемы. Как правило, этот параметр не используется, но может применяться, если необходимо выполнить дополнительные действия в наборе строк схемы перед передачей его в COM\-объект. Время жизни `pSchemaRowset` ограничено `ppRowset`.  
  
## Возвращаемое значение  
 Стандартное значение `HRESULT`.  
  
## Заметки  
 Эта функция реализует универсальный создатель для всех типов наборов строк схемы. Как правило, пользователь не вызывает эту функцию. Ее вызывает реализация карты схемы.  
  
## Требования  
 **Заголовок:** atldb.h  
  
## См. также  
 [Класс IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)   
 [IDBSchemaRowsetImpl Class Members](http://msdn.microsoft.com/ru-ru/e74f6f82-541c-42e7-b4c6-e2d4656a0649)   
 [SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)   
 [Классы схемы Rowset и Typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md)