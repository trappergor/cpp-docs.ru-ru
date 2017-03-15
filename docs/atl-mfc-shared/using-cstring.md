---
title: "Using CString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CString class (Visual C++)"
  - "CString objects, C++ string manipulation"
  - "CString objects, reference counting"
ms.assetid: ed018aaf-8b10-46f9-828c-f9c092dc7609
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Using CString
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В следующих подразделах этого раздела описывается программирование с использованием `CString`.  Справочные сведения о классе `CString` см. в документации по [CStringT](../atl-mfc-shared/reference/cstringt-class.md).  
  
 Чтобы использовать `CString`, включите заголовок `atlstr.h`.  
  
 Классы `CString`, `CStringA` и `CStringW` являются специализациями шаблона класса [CStringT](../atl-mfc-shared/reference/cstringt-class.md) и основаны на типе поддерживаемых символьных данных.  
  
 Объект `CStringW` содержит тип `wchar_t` и поддерживает строки Юникода.  Объект `CStringA` содержит тип `char` и поддерживает строки с однобайтовой и многобайтовой кодировкой.  Объект `CString` поддерживает тип `char` или тип `wchar_t` в зависимости от того, какой символ определен во время компиляции — `MBCS` или `UNICODE`.  
  
 Объект `CString` хранит символьные данные в объекте `CStringData`.  `CString` принимает строки с завершающим байтом `null` в стиле C, однако не сохраняет символ `null` в хранимых символьных данных.  Вместо этого `CString` отслеживает длину строки.  `CString` не предоставляет знак завершения NULL при экспорте строки в стиле C.  Вы можете вставить `null` в `CString`, однако это может привести к непредвиденным результатам.  
  
 Следующий набор строковых классов можно использовать без привязки библиотеки MFC, как с поддержкой CRT, так и без нее: `CAtlString`, `CAtlStringA` и `CAtlStringW`.  
  
 `CString` используется в машинных проектах.  Для проектов с управляемым кодом \(C\+\+\/CLI\) используйте `System::String`.  
  
 Чтобы добавить больше возможностей, чем предлагает `CString`, `CStringA` или `CStringW`, необходимо создать подкласс `CStringT`, содержащий дополнительные компоненты.  
  
 В следующем коде показано создание `CString` и его распечатка в стандартном выводе:  
  
```cpp  
#include <atlstr.h>  
  
int main() {  
    CString aCString = CString(_T("A string"));  
    _tprintf(_T("%s"), (LPCTSTR) aCString);  
}  
```  
  
## В этом подразделе  
 [Базовые операции CString](../atl-mfc-shared/basic-cstring-operations.md)  
 Описывает базовые операции `CString`, включая создание объектов из строковых литералов C, доступ к отдельным символам в `CString`, объединение двух объектов и сравнение объектов `CString`.  
  
 [Управление строковыми данными](../atl-mfc-shared/string-data-management.md)  
 Описывает использование Юникода и многобайтовой кодировки с `CString`.  
  
 [Семантика CString](../atl-mfc-shared/cstring-semantics.md)  
 Поясняет использование объектов `CString`.  
  
 [Операции CString, связанные со строками в стиле C](../atl-mfc-shared/cstring-operations-relating-to-c-style-strings.md)  
 Описывает операции с содержимым объекта `CString` как со строкой с завершающим нулевым байтом в стиле C.  
  
 [Выделение и освобождение памяти для BSTR](../atl-mfc-shared/allocating-and-releasing-memory-for-a-bstr.md)  
 Описывает использование памяти для `BSTR` и COM\-объектов.  
  
 [Очистка исключений CString](../atl-mfc-shared/cstring-exception-cleanup.md)  
 Поясняет, что явная очистка в MFC 3.0 и последующих версий больше не требуется.  
  
 [Передача аргументов CString](../atl-mfc-shared/cstring-argument-passing.md)  
 Поясняет, как передать объекты CString в функции и как вернуть объекты `CString` из функций.  
  
 [Поддержка Юникода и многобайтовой кодировки](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)  
 Описывает реализацию поддержки Юникода и многобайтовой кодировки в MFC.  
  
## Ссылка  
 [CStringT](../atl-mfc-shared/reference/cstringt-class.md)  
 Содержит справочные сведения о классе `CStringT`.  
  
 [CSimpleStringT Class](../atl-mfc-shared/reference/csimplestringt-class.md)  
 Содержит справочные сведения о классе `CSimpleStringT`.  
  
## Связанные подразделы  
 [Строки](../atl-mfc-shared/strings-atl-mfc.md)  
 Содержит ссылки на разделы, в которых описаны несколько способов управления строковыми данными.  
  
 [Создание экземпляра шаблона классов](../Topic/Class%20Template%20Instantiation.md)  
 `CString` представляет собой `typedef`, основанный на `CStringT`, экземпляре специализации шаблона класса.