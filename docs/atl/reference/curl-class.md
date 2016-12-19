---
title: "CUrl Class | Microsoft Docs"
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
  - "ATL.CUrl"
  - "CUrl"
  - "ATL::CUrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUrl class"
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет URL\-адрес.  Его можно управлять независимо от других каждый элемент url\-адреса, разрешает ли анализ существующая строка url\-адреса или построение строку с нуля.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class CUrl  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CUrl::CUrl](../Topic/CUrl::CUrl.md)|Конструктор.|  
|[CUrl::~CUrl](../Topic/CUrl::~CUrl.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CUrl::Canonicalize](../Topic/CUrl::Canonicalize.md)|Этот метод вызывается для преобразования строки url\-адреса в канонической форме.|  
|[CUrl::Clear](../Topic/CUrl::Clear.md)|Вызовите этот метод, чтобы удалить все поля URL\-адрес.|  
|[CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md)|Вызовите этот метод, чтобы расшифровать и анализа url\-адреса.|  
|[CUrl::CreateUrl](../Topic/CUrl::CreateUrl.md)|Вызывайте этот метод для создания url\-адресов.|  
|[CUrl::GetExtraInfo](../Topic/CUrl::GetExtraInfo.md)|Вызовите этот метод, чтобы получить дополнительную информацию \(например ?*text*\) или \#*text*\) об URL\-адресе.|  
|[CUrl::GetExtraInfoLength](../Topic/CUrl::GetExtraInfoLength.md)|Этот метод вызывается для получения длины дополнительного сведения \(например ?*text* или \#*text*\), извлекаемого из url\-адреса.|  
|[CUrl::GetHostName](../Topic/CUrl::GetHostName.md)|Вызовите этот метод, чтобы получить имя узла из url\-адреса.|  
|[CUrl::GetHostNameLength](../Topic/CUrl::GetHostNameLength.md)|Этот метод вызывается для получения длины имени узла.|  
|[CUrl::GetPassword](../Topic/CUrl::GetPassword.md)|Вызовите этот метод, чтобы получить пароль из url\-адреса.|  
|[CUrl::GetPasswordLength](../Topic/CUrl::GetPasswordLength.md)|Вызывайте этот метод для получения длину пароля.|  
|[CUrl::GetPortNumber](../Topic/CUrl::GetPortNumber.md)|Вызовите этот метод, чтобы получить номер порта с точки зрения ATL\_URL\_PORT.|  
|[CUrl::GetScheme](../Topic/CUrl::GetScheme.md)|Вызывайте этот метод для получения схемы URL\-адрес.|  
|[CUrl::GetSchemeName](../Topic/CUrl::GetSchemeName.md)|Вызовите этот метод, чтобы получить имя схемы URL\-адрес.|  
|[CUrl::GetSchemeNameLength](../Topic/CUrl::GetSchemeNameLength.md)|Этот метод вызывается для получения длины имени схемы URL\-адрес.|  
|[CUrl::GetUrlLength](../Topic/CUrl::GetUrlLength.md)|Этот метод вызывается для получения длины URL\-адрес.|  
|[CUrl::GetUrlPath](../Topic/CUrl::GetUrlPath.md)|Вызовите этот метод, чтобы получить путь url\-адреса.|  
|[CUrl::GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md)|Этот метод вызывается для получения длины пути url\-адреса.|  
|[CUrl::GetUserName](../Topic/CUrl::GetUserName.md)|Вызовите этот метод, чтобы получить имя пользователя из url\-адреса.|  
|[CUrl::GetUserNameLength](../Topic/CUrl::GetUserNameLength.md)|Этот метод вызывается для получения длины имени пользователя.|  
|[CUrl::SetExtraInfo](../Topic/CUrl::SetExtraInfo.md)|Вызовите этот метод, чтобы установить дополнительную информацию \(например ?*text* или \#*text*\) URL\-адрес.|  
|[CUrl::SetHostName](../Topic/CUrl::SetHostName.md)|Вызывайте этот метод для задания имени узла.|  
|[CUrl::SetPassword](../Topic/CUrl::SetPassword.md)|Вызовите этот метод, чтобы задать пароль.|  
|[CUrl::SetPortNumber](../Topic/CUrl::SetPortNumber.md)|Вызовите этот метод, чтобы задать номер порта в терминах ATL\_URL\_PORT.|  
|[CUrl::SetScheme](../Topic/CUrl::SetScheme.md)|Вызовите этот метод, чтобы установить схему URL\-адрес.|  
|[CUrl::SetSchemeName](../Topic/CUrl::SetSchemeName.md)|Вызовите этот метод, чтобы задать имя схемы URL\-адрес.|  
|[CUrl::SetUrlPath](../Topic/CUrl::SetUrlPath.md)|Вызовите этот метод, чтобы задать путь url\-адреса.|  
|[CUrl::SetUserName](../Topic/CUrl::SetUserName.md)|Вызывайте этот метод для задания имени пользователя.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CUrl::operator \=](../Topic/CUrl::operator%20=.md)|Присвоит `CUrl` указанный объект текущему объекту `CUrl`.|  
  
## Заметки  
 `CUrl` позволяет управлять поля URL\-адрес в виде пути или номер порта.  `CUrl` понимает URL\-адрес, имеет следующую форму:  
  
 \<Scheme\>:\/\/\<UserName\>:\<Password\>@\<HostName\>:\<PortNumber\>\/\<UrlPath\>\<ExtraInfo\>  
  
 Некоторые поля \(необязательно\). Например, рассмотрим этот URL\-адрес:  
  
 http:\/\/someone:secret@www.microsoft.com:80\/visualc\/stuff.htm\#contents  
  
 [CUrl::CrackUrl](../Topic/CUrl::CrackUrl.md) анализирует его следующим образом:  
  
-   Схема: "HTTP" или [ATL\_URL\_SCHEME\_HTTP](../Topic/ATL_URL_SCHEME.md)  
  
-   Имя пользователя. "someone"  
  
-   Пароль: "секрет"  
  
-   Hostname: "www.microsoft.com"  
  
-   PortNumber: 80  
  
-   UrlPath: "visualc\/stuff.htm"  
  
-   ExtraInfo: "\#contents"  
  
 Для управления " поле UrlPath \(например, можно использовать [GetUrlPath](../Topic/CUrl::GetUrlPath.md), [GetUrlPathLength](../Topic/CUrl::GetUrlPathLength.md) и [SetUrlPath](../Topic/CUrl::SetUrlPath.md).  Можно использовать [CreateUrl](../Topic/CUrl::CreateUrl.md) чтобы создать полную строку с url\-адресом.  
  
## Требования  
 **Header:** atlutil.h  
  
## См. также  
 [Классы](../../atl/reference/atl-classes.md)