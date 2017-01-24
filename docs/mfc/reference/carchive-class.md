---
title: "CArchive Class | Microsoft Docs"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive class"
  - "data storage [C++], CArchive class"
  - "I/O [MFC], archiving objects"
  - "сериализация [C++], CArchive class"
  - "storage [C++], CArchive class"
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArchive Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет сохранить сложную сеть объектов в постоянной бинарной форме \(обычно запоминающем устройстве\), которая повторяется после создания эти объекты, в свою очередь, удалены.  
  
## Синтаксис  
  
```  
class CArchive  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CArchive::CArchive](../Topic/CArchive::CArchive.md)|Создает объект `CArchive`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CArchive::Abort](../Topic/CArchive::Abort.md)|Закрывает архив без вызова исключения.|  
|[CArchive::Close](../Topic/CArchive::Close.md)|Сбрасывает неписаные данные и отключается от `CFile`.|  
|[CArchive::Flush](../Topic/CArchive::Flush.md)|Сведения о записыватей на диск из буфера неписаные архива.|  
|[CArchive::GetFile](../Topic/CArchive::GetFile.md)|Получает указатель объекта `CFile` для этого архива.|  
|[CArchive::GetObjectSchema](../Topic/CArchive::GetObjectSchema.md)|Вызванный из функции `Serialize` для указания версии объекта, который десериализуется.|  
|[CArchive::IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md)|Определяет, является ли опорожнялся буфере во время Windows sockets возвращает процесс.|  
|[CArchive::IsLoading](../Topic/CArchive::IsLoading.md)|Указывает, загружает ли в архиве.|  
|[CArchive::IsStoring](../Topic/CArchive::IsStoring.md)|Указывает, хранятся ли в архиве.|  
|[CArchive::MapObject](../Topic/CArchive::MapObject.md)|Задает объекты в сопоставлении, не сериализованы к файлу, но которые доступны для subobjects ссылки.|  
|[CArchive::Read](../Topic/CArchive::Read.md)|Считывает необработанные байты.|  
|[CArchive::ReadClass](../Topic/CArchive::ReadClass.md)|Считывает ссылку класса ранее сохраненные с `WriteClass`.|  
|[CArchive::ReadObject](../Topic/CArchive::ReadObject.md)|Вызывает функцию `Serialize` объекта для загрузки.|  
|[CArchive::ReadString](../Topic/CArchive::ReadString.md)|Считывает одну линию текста.|  
|[CArchive::SerializeClass](../Topic/CArchive::SerializeClass.md)|Считывает или записывает ссылку на объект класса `CArchive` в зависимости от направления `CArchive`.|  
|[CArchive::SetLoadParams](../Topic/CArchive::SetLoadParams.md)|Устанавливает размер, до которого массив загрузки.  Быть вызываются, прежде чем любой объект загружен или до `MapObject` или `ReadObject` Вызываются.|  
|[CArchive::SetObjectSchema](../Topic/CArchive::SetObjectSchema.md)|Устанавливает схему объекта, сохраненный в объекте архива.|  
|[CArchive::SetStoreParams](../Topic/CArchive::SetStoreParams.md)|Задает размер хэш\-таблицы и размер блока сопоставления, используемого для идентификации уникального объекты в процессе сериализации.|  
|[CArchive::Write](../Topic/CArchive::Write.md)|Записывает необработанные байты.|  
|[CArchive::WriteClass](../Topic/CArchive::WriteClass.md)|Регистрирует ссылку на `CRuntimeClass` к `CArchive`.|  
|[CArchive::WriteObject](../Topic/CArchive::WriteObject.md)|Вызывает функцию `Serialize` объекта для хранения.|  
|[CArchive::WriteString](../Topic/CArchive::WriteString.md)|Записывает одинарная линия текста.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CArchive::operator \<\<](../Topic/CArchive::operator%20%3C%3C.md)|Объекты и типы\-примитивы магазинов по архивации.|  
|[CArchive::operator \>\>](../Topic/CArchive::operator%20%3E%3E.md)|Объекты и типы\-примитивы загрузок из архива.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CArchive::m\_pDocument](../Topic/CArchive::m_pDocument.md)||  
  
## Заметки  
 `CArchive` не имеет базовый класс.  
  
 Далее можно загрузить объекты из постоянного хранилища, воспроизводя их в памяти.  Этот процесс внесения данные постоянных вызвать "сериализацией."  
  
 Можно представить себе объекта архива в качестве типа бинарный stream.  Как поток ввода\-вывода, в архиве связать с файлом и разрешает buffered запись и чтение данных и из хранилища.  Последовательности процессов потока ввода\-вывода символов ASCII, но архив процесса двоичные данные объекта в эффективным, nonredundant формате.  
  
 Необходимо создать объект [CFile](../../mfc/reference/cfile-class.md) прежде, чем можно будет создать объект `CArchive`.  Кроме того, следует убедиться в том, что состояние загрузки\/хранилища архива совместимо с режимом файлов открыть.  Вы ограничены один активный файл в файл.  
  
 При создании объекта `CArchive`, вложите его к объекту класса `CFile` \(или производного класса\), представляющий открытый файл.  Можно также указать, будет ли архив используется для загрузки и хранения.  Объект `CArchive` не может обрабатывать только типы\-примитивы, а также возражает [CObject](../Topic/CObject%20Class.md)\- производных классов, предназначенных для сериализации.  Сериализуемый класс обычно имеет функции\-члена `Serialize`, и обычно он используется макрос [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) и [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md), как описано ниже классом `CObject`.  
  
 Перегруженные операторы извлечения \(**\>\>**\) и insert \(**\<\<**\) удобные программные интерфейсы архива, которые поддерживают как типы\-примитивы и `CObject`\- производные классы.  
  
 Программирование с `CArchive` также обозреватель Windows и [CSocketFile](../Topic/CSocketFile%20Class.md) sockets MFC classify [CSocket](../../mfc/reference/csocket-class.md).  Поддержка функции\-члена [IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md), потребление.  
  
 Дополнительные сведения о `CArchive` см. в разделе статьи [сериализация](../Topic/Serialization%20in%20MFC.md) и [Windows sockets: Использование сокета с архивами](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## Иерархия наследования  
 `CArchive`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CObject Class](../Topic/CObject%20Class.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)   
 [CSocketFile Class](../Topic/CSocketFile%20Class.md)