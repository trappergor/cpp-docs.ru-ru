---
title: "CPathT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CPathT"
  - "CPathT"
  - "ATL::CPathT<StringType>"
  - "ATL::CPathT"
  - "ATL.CPathT<StringType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CPathT class"
ms.assetid: eba4137d-1fd2-4b44-a2e1-0944db64df3c
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CPathT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет путь.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template< typename   
      StringType  
      >   
class CPathT  
```  
  
#### Параметры  
 `StringType`  
 Класс строки ATL\/MFC, используемый для пути \(см. [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)\).  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CPathT::PCXSTR](../Topic/CPathT::PCXSTR.md)|Константы типа string.|  
|[CPathT::PXSTR](../Topic/CPathT::PXSTR.md)|Строковый тип.|  
|[CPathT::XCHAR](../Topic/CPathT::XCHAR.md)|Символьный тип.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPathT::CPathT](../Topic/CPathT::CPathT.md)|Конструктор для пути.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPathT::AddBackslash](../Topic/CPathT::AddBackslash.md)|Вызовите этот метод, чтобы добавить обратная косая черта в конце строки для создания правильного синтаксиса для пути.|  
|[CPathT::AddExtension](../Topic/CPathT::AddExtension.md)|Вызовите этот метод, чтобы добавить расширение файла в пути.|  
|[CPathT::Append](../Topic/CPathT::Append.md)|Вызывайте этот метод для добавления строки в текущем пути.|  
|[CPathT::BuildRoot](../Topic/CPathT::BuildRoot.md)|Вызывайте этот метод для создания путь корня из заданного числа диска.|  
|[CPathT::Canonicalize](../Topic/CPathT::Canonicalize.md)|Этот метод вызывается для преобразования пути к канонической форме.|  
|[CPathT::Combine](../Topic/CPathT::Combine.md)|Вызовите этот метод, чтобы сцепить строка, представляющая имя каталога и строка, представляющая имя пути к файлу в один путь.|  
|[CPathT::CommonPrefix](../Topic/CPathT::CommonPrefix.md)|Этот метод следует вызывать, чтобы определить, использует ли указанный путь общий префикс с текущим местоположением.|  
|[CPathT::CompactPath](../Topic/CPathT::CompactPath.md)|Вызовите этот метод, чтобы усечь путь к файлу приспособления в пределах заданной ширины точки, заменив компоненты пути с точками.|  
|[CPathT::CompactPathEx](../Topic/CPathT::CompactPathEx.md)|Вызовите этот метод, чтобы усечь путь к файлу приспособления в заданное количество символов, заменив компоненты пути с точками.|  
|[CPathT::FileExists](../Topic/CPathT::FileExists.md)|Вызовите этот метод, чтобы проверить, существует ли файл для этого имени пути.|  
|[CPathT::FindExtension](../Topic/CPathT::FindExtension.md)|Вызовите этот метод, чтобы найти положение расширения файла в путь.|  
|[CPathT::FindFileName](../Topic/CPathT::FindFileName.md)|Вызовите этот метод, чтобы найти местоположение имени файла в путь.|  
|[CPathT::GetDriveNumber](../Topic/CPathT::GetDriveNumber.md)|Вызовите этот метод, чтобы найти путь для буквы диска в диапазоне от "a" до "Z" и возвращать соответствующий номер диска.|  
|[CPathT::GetExtension](../Topic/CPathT::GetExtension.md)|Вызовите этот метод, чтобы получить расширение файла из пути.|  
|[CPathT::IsDirectory](../Topic/CPathT::IsDirectory.md)|Вызывайте этот метод для проверки, является ли путь допустимый каталог.|  
|[CPathT::IsFileSpec](../Topic/CPathT::IsFileSpec.md)|Вызовите этот метод, чтобы найти путь для всех путь\- выделение символов \(например, ": " или "\\ "\).  Если путь\- символы\-разделители, присутствующие, то считается, что путь, спецификаций файла.|  
|[CPathT::IsPrefix](../Topic/CPathT::IsPrefix.md)|Этот метод следует вызывать, чтобы определить, содержит ли путь допустимый префикс типа, переданного `pszPrefix`.|  
|[CPathT::IsRelative](../Topic/CPathT::IsRelative.md)|Вызовите этот метод, чтобы определить, является ли путь относительным.|  
|[CPathT::IsRoot](../Topic/CPathT::IsRoot.md)|Этот метод следует вызывать, чтобы определить, что путь корень каталога.|  
|[CPathT::IsSameRoot](../Topic/CPathT::IsSameRoot.md)|Этот метод следует вызывать, чтобы определить, имеет ли другой путь корневого компонента общего с текущим местоположением.|  
|[CPathT::IsUNC](../Topic/CPathT::IsUNC.md)|Этот метод следует вызывать, чтобы определить, является ли путь \(допустимый путь в формате универсального соглашения об именовании\) и общей папки сервера.|  
|[CPathT::IsUNCServer](../Topic/CPathT::IsUNCServer.md)|Этот метод следует вызывать, чтобы определить, является ли путь допустимый путь универсального соглашения об именовании \(UNC\) сервера.|  
|[CPathT::IsUNCServerShare](../Topic/CPathT::IsUNCServerShare.md)|Этот метод следует вызывать, чтобы определить, является ли путь допустимый путь к общей папке в формате универсального соглашения об именовании \(UNC\), \\\\*сервер*\\*общая папка*.|  
|[CPathT::MakePretty](../Topic/CPathT::MakePretty.md)|Этот метод вызывается для преобразования пути ко всем нижний регистр символов для предоставления согласованного внешнего вида пути.|  
|[CPathT::MatchSpec](../Topic/CPathT::MatchSpec.md)|Вызовите этот метод, чтобы найти путь для строки, содержащей тип соответствия с подстановочными знаками.|  
|[CPathT::QuoteSpaces](../Topic/CPathT::QuoteSpaces.md)|Вызовите этот метод, чтобы заключить путь в кавычки, если он содержит какие\-либо пробелы.|  
|[CPathT::RelativePathTo](../Topic/CPathT::RelativePathTo.md)|Вызывайте этот метод для создания относительный путь из одного файла или папки в другое.|  
|[CPathT::RemoveArgs](../Topic/CPathT::RemoveArgs.md)|Вызовите этот метод, чтобы удалить все аргументы командной строки из пути.|  
|[CPathT::RemoveBackslash](../Topic/CPathT::RemoveBackslash.md)|Вызовите этот метод, чтобы удалить завершающий символ косой черты из пути.|  
|[CPathT::RemoveBlanks](../Topic/CPathT::RemoveBlanks.md)|Вызовите этот метод, чтобы удалить все начальные и конечные пробелы из пути.|  
|[CPathT::RemoveExtension](../Topic/CPathT::RemoveExtension.md)|Вызовите этот метод, чтобы удалить расширение файла из пути, если он имеется.|  
|[CPathT::RemoveFileSpec](../Topic/CPathT::RemoveFileSpec.md)|Вызовите этот метод, чтобы удалить завершающий имя файла из пути и обратная косая черта, если он имеет их.|  
|[CPathT::RenameExtension](../Topic/CPathT::RenameExtension.md)|Вызовите этот метод, чтобы заменить расширение имени файла в пути с новым расширением.  Если имя файла не содержит расширения, то расширение будет присоединяется до конца строки.|  
|[CPathT::SkipRoot](../Topic/CPathT::SkipRoot.md)|Вызовите этот метод, чтобы проанализировать путь на части буквы диска или сервера\/путь в общую папку UNC.|  
|[CPathT::StripPath](../Topic/CPathT::StripPath.md)|Вызовите этот метод, чтобы удалить часть пути полного пути и имени файла.|  
|[CPathT::StripToRoot](../Topic/CPathT::StripToRoot.md)|Вызовите этот метод, чтобы удалить все части пути, за исключением корневого данных.|  
|[CPathT::UnquoteSpaces](../Topic/CPathT::UnquoteSpaces.md)|Вызывайте этот метод для удаления кавычки из начала и конца пути.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CPathT::operator const StringType &](../Topic/CPathT::operator%20const%20StringType%20&.md)|Этот оператор позволяет объекту, отображаемый в виде строки.|  
|[CPathT::operator CPathT::PCXSTR](../Topic/CPathT::operator%20CPathT::PCXSTR.md)|Этот оператор позволяет объекту, отображаемый в виде строки.|  
|[CPathT::operator StringType &](../Topic/CPathT::operator%20StringType%20&.md)|Этот оператор позволяет объекту, отображаемый в виде строки.|  
|[CPathT::operator \+\=](../Topic/CPathT::operator%20+=.md)|Этот оператор добавляет строку в пути.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CPathT::m\_strPath](../Topic/CPathT::m_strPath.md)|Путь.|  
  
## Заметки  
 `CPath`, `CPathA` и `CPathW` указанных экземпляров `CPathT` следующим образом:  
  
 `typedef CPathT< CString > CPath;`  
  
 `typedef CPathT< CStringA > CPathA;`  
  
 `typedef CPathT< CStringW > CPathW;`  
  
## Требования  
 **Header:** atlpath.h  
  
## См. также  
 [Классы](../../atl/reference/atl-classes.md)   
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)