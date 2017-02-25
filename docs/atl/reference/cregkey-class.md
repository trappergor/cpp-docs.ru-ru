---
title: "CRegKey Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRegKey"
  - "ATL::CRegKey"
  - "ATL.CRegKey"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, реестр"
  - "CRegKey class"
  - "реестр, удаление ключей"
  - "реестр, удаление значений"
  - "реестр, запись в"
ms.assetid: 3afce82b-ba2c-4c1a-8404-dc969e1af74b
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CRegKey Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для работы с записи в реестре системы.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CRegKey  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRegKey::CRegKey](../Topic/CRegKey::CRegKey.md)|Конструктор.|  
|[CRegKey::~CRegKey](../Topic/CRegKey::~CRegKey.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRegKey::Attach](../Topic/CRegKey::Attach.md)|Вызовите этот метод, чтобы вложить HKEY к объекту `CRegKey` с помощью маркера участника [m\_hKey](../Topic/CRegKey::m_hKey.md) к `hKey`.|  
|[CRegKey::Close](../Topic/CRegKey::Close.md)|Этот метод вызывается для освобождения дескриптора элемента [m\_hKey](../Topic/CRegKey::m_hKey.md) и установить его на значение NULL.|  
|[CRegKey::Create](../Topic/CRegKey::Create.md)|Вызывайте этот метод для создания заданным ключом, если она не существует, как подраздел `hKeyParent`.|  
|[CRegKey::DeleteSubKey](../Topic/CRegKey::DeleteSubKey.md)|Вызывайте этот метод для удаления указанный ключ из реестра.|  
|[CRegKey::DeleteValue](../Topic/CRegKey::DeleteValue.md)|Вызовите этот метод, чтобы удалить поле значения из [m\_hKey](../Topic/CRegKey::m_hKey.md).|  
|[CRegKey::Detach](../Topic/CRegKey::Detach.md)|Вызывайте этот метод для удаления дескриптора элемента, наконец [m\_hKey](../Topic/CRegKey::m_hKey.md) из объекта `CRegKey` и set `m_hKey` значение NULL.|  
|[CRegKey::EnumKey](../Topic/CRegKey::EnumKey.md)|Вызовите этот метод, чтобы выполнить перечисление подразделов открытого раздела реестра.|  
|[CRegKey::Flush](../Topic/CRegKey::Flush.md)|Вызовите этот метод, чтобы записать все атрибуты открытого раздела реестра в реестр.|  
|[CRegKey::GetKeySecurity](../Topic/CRegKey::GetKeySecurity.md)|Вызывайте этот метод для извлечения копией дескриптора безопасности, защищая открыть раздел реестра.|  
|[CRegKey::NotifyChangeKeyValue](../Topic/CRegKey::NotifyChangeKeyValue.md)|Этот метод уведомляет вызывающий об изменениях к атрибутам или содержимое открытого раздела реестра.|  
|[CRegKey::Open](../Topic/CRegKey::Open.md)|Вызовите этот метод, чтобы открыть указанный ключ и set [m\_hKey](../Topic/CRegKey::m_hKey.md) на маркер этого ключа.|  
|[CRegKey::QueryBinaryValue](../Topic/CRegKey::QueryBinaryValue.md)|Этот метод вызывается для получения двоичных данных для имени указанного значения.|  
|[CRegKey::QueryDWORDValue](../Topic/CRegKey::QueryDWORDValue.md)|Этот метод вызывается для получения данных DWORD для имени указанного значения.|  
|[CRegKey::QueryGUIDValue](../Topic/CRegKey::QueryGUIDValue.md)|Вызывайте этот метод для извлечения сведений о GUID для имени указанного значения.|  
|[CRegKey::QueryMultiStringValue](../Topic/CRegKey::QueryMultiStringValue.md)|Вызывайте этот метод для извлечения сведений о multistring для имени указанного значения.|  
|[CRegKey::QueryQWORDValue](../Topic/CRegKey::QueryQWORDValue.md)|Вызывайте этот метод для извлечения сведений о QWORD для имени указанного значения.|  
|[CRegKey::QueryStringValue](../Topic/CRegKey::QueryStringValue.md)|Вызовите этот метод, чтобы получить данные строк для имени указанного значения.|  
|[CRegKey::QueryValue](../Topic/CRegKey::QueryValue.md)|Этот метод вызывается для получения данных для поля указанного значения [m\_hKey](../Topic/CRegKey::m_hKey.md).  Более ранние версии этого метода более не поддерживаются и не помечены как **ATL\_DEPRECATED**.|  
|[CRegKey::RecurseDeleteKey](../Topic/CRegKey::RecurseDeleteKey.md)|Вызывайте этот метод для удаления указанный ключ из реестра и явно удалить все подразделов.|  
|[CRegKey::SetBinaryValue](../Topic/CRegKey::SetBinaryValue.md)|Вызывайте этот метод для задания бинарный значение раздела реестра.|  
|[CRegKey::SetDWORDValue](../Topic/CRegKey::SetDWORDValue.md)|Вызовите этот метод, чтобы установить значение DWORD раздела реестра.|  
|[CRegKey::SetGUIDValue](../Topic/CRegKey::SetGUIDValue.md)|Вызовите этот метод, чтобы установить значение GUID раздела реестра.|  
|[CRegKey::SetKeySecurity](../Topic/CRegKey::SetKeySecurity.md)|Вызовите этот метод, чтобы установить безопасность раздела реестра.|  
|[CRegKey::SetKeyValue](../Topic/CRegKey::SetKeyValue.md)|Этот метод вызывается для хранения данных в поле указанного значения заданного ключа.|  
|[CRegKey::SetMultiStringValue](../Topic/CRegKey::SetMultiStringValue.md)|Вызовите этот метод, чтобы установить значение multistring раздела реестра.|  
|[CRegKey::SetQWORDValue](../Topic/CRegKey::SetQWORDValue.md)|Вызовите этот метод, чтобы установить значение QWORD раздела реестра.|  
|[CRegKey::SetStringValue](../Topic/CRegKey::SetStringValue.md)|Вызовите этот метод, чтобы задать строковое значение раздела реестра.|  
|[CRegKey::SetValue](../Topic/CRegKey::SetValue.md)|Этот метод вызывается для хранения данных в поле указанного значения [m\_hKey](../Topic/CRegKey::m_hKey.md).  Более ранние версии этого метода более не поддерживаются и не помечены как **ATL\_DEPRECATED**.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRegKey::operator HKEY](../Topic/CRegKey::operator%20HKEY.md)|Преобразует объект `CRegKey` к HKEY.|  
|[CRegKey::operator \=](../Topic/CRegKey::operator%20=.md)|Оператор присваивания.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CRegKey::m\_hKey](../Topic/CRegKey::m_hKey.md)|Содержит дескриптор раздела реестра, связанного с объектом `CRegKey`.|  
|[CRegKey::m\_pTM](../Topic/CRegKey::m_pTM.md)|Указатель на объект `CAtlTransactionManager`|  
  
## Заметки  
 `CRegKey` предоставляет методы для создания и удаление ключей и значений в реестре системы.  Реестр содержит набор установка\- для конкретных определений элементов системы, например номера версии программы, логически\-к\- физические сопоставления задания оборудования и COM\-объект.  
  
 `CRegKey` обеспечивает интерфейс программирования реестру системы для данного компьютера.  Например, чтобы открыть указанный раздел реестра, вызов `CRegKey::Open`.  Извлекать или изменять значение данных, вызовите `CRegKey::QueryValue` или `CRegKey::SetValue` соответственно.  Закрыть ключ, вызовите `CRegKey::Close`.  
  
 Если закрыть ключ, его данные реестра записаны \(потопленный\) на жесткий диск.  Этот процесс может занять несколько секунд.  Если приложение должно явно записывать данные реестра на жесткий диск, можно вызвать функцию [RegFlushKey](http://msdn.microsoft.com/library/windows/desktop/ms724867) Win32.  Однако **RegFlushKey** использует много системных ресурсов и только после вызываются должно быть совершенно обязательный.  
  
> [!IMPORTANT]
>  Все методы, позволяющие вызывающему объекту, чтобы определить расположение в реестре имеет возможность считывать данные, которые нельзя доверять.  Методы, которые используют [RegQueryValueEx](http://msdn.microsoft.com/library/windows/desktop/ms724911) принять во внимание, что эта функция не обрабатывает строки, которые явно завершенных NULL.  Оба условия должны иметь проверены для вызывающего кода.  
  
## Требования  
 **Header:**  atlbase.h  
  
## См. также  
 [Образец DCOM](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Registry Overview](http://msdn.microsoft.com/library/windows/desktop/ms724871)   
 [Registry Functions](http://msdn.microsoft.com/library/windows/desktop/ms724875)   
 [Registry Value Types](http://msdn.microsoft.com/library/windows/desktop/ms724884)