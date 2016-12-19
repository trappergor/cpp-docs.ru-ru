---
title: "CRowset::Insert | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>.Insert"
  - "CRowset.Insert"
  - "CRowset<TAccessor>.Insert"
  - "CRowset<TAccessor>::Insert"
  - "ATL::CRowset<TAccessor>::Insert"
  - "ATL.CRowset.Insert"
  - "CRowset::Insert"
  - "ATL::CRowset::Insert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Insert - метод"
ms.assetid: 6a64a1c3-10ac-4296-8685-0fd6fe63a13b
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Insert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает и инициализирует новую строку с использованием данных из метода доступа.  
  
## Синтаксис  
  
```  
  
      HRESULT Insert(   
   int nAccessor = 0,   
   bool bGetHRow = false    
) throw( );  
```  
  
#### Параметры  
 `nAccessor`  
 \[in\] число доступа используется для вставки данных.  
  
 *bGetHRow*  
 \[in\] указывает, является ли извлечь дескриптор для введенной строки.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Этот метод требует дополнительного интерфейса `IRowsetChange`, может не поддерживаться во всех поставщиках; если это так, метод возвращает **E\_NOINTERFACE**.  Необходимо также установить **DBPROP\_IRowsetChange** в `VARIANT_TRUE` до вызова метода **Открыть** на таблице или команда, содержащий набор строк.  
  
 Вставка может вылтить сбоя, если один или несколько столбцов недоступны для записи.  Чтобы устранить эти ошибки, измените таблицу курсоров.  
  
## Пример  
 В следующем примере показано, как получить доступ к источнику данных через набор строк, а затем вставить строку с таблицей в этом наборе строк.  
  
 Сначала создайте класс таблицы можно вставить новый объект ATL в проект.  Например, щелкните правой кнопкой мыши проект на панели рабочей области и выберите **Новый объект ATL**.  В категории **Data Access**, выберите **Потребитель**.  Создайте объект объект\-получателя типа **Таблица**. \(Выбор **Таблица** создает набор строк непосредственно из таблицы. выбор **Команда** создает набор строк с помощью команды SQL\). Выберите источник данных, указав таблицу через, чтобы получить доступ к этому источнику данных.  При вызове этот объект **CCustomerTable** объект\-получателя, затем будет реализован код вставки следующим образом:  
  
 [!code-cpp[NVC_OLEDB_Consumer#10](../../data/oledb/codesnippet/CPP/crowset-insert_1.cpp)]  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CRowset](../Topic/CRowset%20Class.md)