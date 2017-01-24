---
title: "CAtlTransactionManager Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlTransactionManager"
  - "atltransactionmanager/ATL::CAtlTransactionManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTransactionManager class"
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlTransactionManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс содержит программу\-оболочку CAtlTransactionManager функции диспетчера транзакций ядра \(KTM\).  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
class CAtlTransactionManager;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlTransactionManager::~CAtlTransactionManager](../Topic/CAtlTransactionManager::~CAtlTransactionManager.md)|Деструктор CAtlTransactionManager.|  
|[CAtlTransactionManager::CAtlTransactionManager](../Topic/CAtlTransactionManager::CAtlTransactionManager.md)|Конструктор CAtlTransactionManager.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlTransactionManager::Close](../Topic/CAtlTransactionManager::Close.md)|Закрывает один дескриптор транзакции.|  
|[CAtlTransactionManager::Commit](../Topic/CAtlTransactionManager::Commit.md)|Запросы, зафиксированной транзакции.|  
|[CAtlTransactionManager::Create](../Topic/CAtlTransactionManager::Create.md)|Создает дескриптор транзакции.|  
|[CAtlTransactionManager::CreateFile](../Topic/CAtlTransactionManager::CreateFile.md)|Создает или открывает файл, файловый поток или каталог, как операция транзакции.|  
|[CAtlTransactionManager::DeleteFile](../Topic/CAtlTransactionManager::DeleteFile.md)|Удаляет существующий файл как операция транзакции.|  
|[CAtlTransactionManager::FindFirstFile](../Topic/CAtlTransactionManager::FindFirstFile.md)|Ищет каталог для файлов или подкаталога как транзакционные операции.|  
|[CAtlTransactionManager::GetFileAttributes](../Topic/CAtlTransactionManager::GetFileAttributes.md)|Получение атрибутов файловой системы для заданного файла или каталога в транзакционные операции.|  
|[CAtlTransactionManager::GetFileAttributesEx](../Topic/CAtlTransactionManager::GetFileAttributesEx.md)|Получение атрибутов файловой системы для заданного файла или каталога в транзакционные операции.|  
|[CAtlTransactionManager::GetHandle](../Topic/CAtlTransactionManager::GetHandle.md)|Возвращает дескриптор транзакции.|  
|[CAtlTransactionManager::IsFallback](../Topic/CAtlTransactionManager::IsFallback.md)|Указывает, включаются ли вызовы перехода на запасные ресурсы.|  
|[CAtlTransactionManager::MoveFile](../Topic/CAtlTransactionManager::MoveFile.md)|Перемещает существующий файл или каталог, включая его дочерние элементы, такие как асинхронную операцию.|  
|[CAtlTransactionManager::RegCreateKeyEx](../Topic/CAtlTransactionManager::RegCreateKeyEx.md)|Создает указанный раздел реестра и связывает его с транзакцией.  Если ключ уже существует, то функция позволяет открыть его.|  
|[CAtlTransactionManager::RegDeleteKey](../Topic/CAtlTransactionManager::RegDeleteKey.md)|Удаление подраздела и его значения из указанного представления платформа\- определенной реестра, как операция транзакции.|  
|[CAtlTransactionManager::RegOpenKeyEx](../Topic/CAtlTransactionManager::RegOpenKeyEx.md)|Открывается указанный раздел реестра и связывает его с транзакцией.|  
|[CAtlTransactionManager::Rollback](../Topic/CAtlTransactionManager::Rollback.md)|Запросы, транзакции откатила.|  
|[CAtlTransactionManager::SetFileAttributes](../Topic/CAtlTransactionManager::SetFileAttributes.md)|Задает атрибуты для файла или каталога, например асинхронную операцию.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlTransactionManager::m\_bFallback](../Topic/CAtlTransactionManager::m_bFallback.md)|`TRUE` если резервирование поддерживается. `FALSE` в противном случае.|  
|[CAtlTransactionManager::m\_hTransaction](../Topic/CAtlTransactionManager::m_hTransaction.md)|Дескриптор транзакции.|  
  
## Заметки  
  
## Иерархия наследования  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## Требования  
 **Header:**  atltransactionmanager.h  
  
## См. также  
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)