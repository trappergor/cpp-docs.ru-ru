---
title: "Exporting String Classes Using CStringT | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringT class, exporting strings"
ms.assetid: bdfc441e-8d2a-461c-9885-46178066c09f
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exporting String Classes Using CStringT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В прошлом, разработчики MFC, производного от `CString` для специализировать собственные классы строки.  В Microsoft Visual C\+\+ .NET 8,0 \(MFC\), класс [CString](../atl-mfc-shared/using-cstring.md) был заменен классом шаблона [CStringT](../atl-mfc-shared/reference/cstringt-class.md) вызова.  Это ожидания несколько преимуществ:  
  
-   Это позволить класс MFC `CString` для использования в проектах библиотеки ATL, не связывая в более крупной или статической библиотеке DLL MFC.  
  
-   С новым классом шаблона `CStringT`, можно настраивать функциональности `CString` использование параметров шаблона символов, подобные признаки, которые определяют к шаблонам в стандартной библиотеки шаблонов \(STL\).  
  
-   При экспорте собственный класс строки из библиотеки DLL с помощью `CStringT` компилятор также автоматически экспортирует базовый класс `CString`.  Поскольку `CString` является классом шаблона, он может быть создан компилятором при использовании если компилятор не узнает об импортироватьо, что `CString` из библиотеки DLL.  Если перенесенных проектов, созданных в Visual C\+\+ 6,0 в Visual C\+\+ .NET, можно увидеть ошибки компоновщика умножать\- символов для заданного `CString` из\-за конфликта `CString` импортированного из библиотеки DLL и локально создавать версии.  Правильный способ это сделать \- описан ниже.  Дополнительные сведения об этом этой проблеме см. в статье базы знаний Майкрософт "связывание ошибки при импорте CString\- производные классы" \(Q309801\) на компакт\-диске библиотеки MSDN или на [http:\/\/support.microsoft.com\/default.aspx](http://support.microsoft.com/default.aspx).  
  
 Следующий сценарий создает компоновщик возникать ошибки символов для умножает определенные классы.  Предположим, что необходимо экспортировать `CString`\- производный класс \(`CMyString`\) из библиотеки DLL расширения MFC:  
  
 [!CODE [NVC_MFC_DLL#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#6)]  
  
 Код объекта\-получателя используется смесь `CString` и `CMyString`. "  MyString.h" не включается в предварительно скомпилированного заголовка и некоторое потребление `CString` не имеет `CMyString` видимый.  
  
 Предположим, что необходимо использовать классы `CString` и `CMyString` в отдельных исходных файлов, Source1.cpp и Source2.cpp.  В Source1.cpp используется `CMyString` и \#include MyString.h.  В Source2.cpp используется `CString`, но не сделать \#include MyString.h.  В этом случае компоновщик пожалуется о `CStringT` быть умножает заданный.  Это вызвано `CString` и импортирована из библиотеки DLL, которая экспортирует `CMyString` и создается локально компилятором с помощью шаблона `CStringT`.  
  
 Чтобы разрешить эту проблему, выполните следующие действия:  
  
 Экспортировать `CStringA` и `CStringW` \(и необходимые базовые классы\) из MFC90.DLL.  Проекты, которые включают MFC всегда будут использовать MFC `CStringA`, экспортированный библиотеки DLL и `CStringW`, как в предыдущих реализациях MFC.  
  
 Затем создайте экспортируемые производный класс, используя шаблон `CStringT`, как `CStringT_Exported` ниже, например:  
  
 [!CODE [NVC_MFC_DLL#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#7)]  
  
 В AfxStr.h замените предыдущее `CString`, `CStringA` и typedef `CStringW` следующим образом:  
  
 [!CODE [NVC_MFC_DLL#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_DLL#8)]  
  
 Несколько предостережений:  
  
-   Не следует экспортировать `CStringT` самого поскольку это приведет к проекты Библиотеки ATL \- только экспортировать специализированный класс `CStringT`.  
  
-   Использование экспортируемые производный класс от `CStringT` свернуть `CStringT` реализуют функциональность re\-.  Дополнительный код ограничена переадресованы конструкторы к базовому классу `CStringT`.  
  
-   `CString`, `CStringA` и `CStringW` должны быть помечен как `__declspec(dllexport/dllimport)` при построении с dll\-библиотекой MFC для совместного использования.  При статической компоновке с библиотекой MFC не следует пометить эти классы экспортироватьо; в противном случае – `CString` для внутреннего использования, `CStringA` и `CStringW` в библиотеке DLL пользователя помечает `CString` как экспортироватьо.  
  
## Связанные разделы  
 [CStringT Class](../atl-mfc-shared/reference/cstringt-class.md)  
  
## См. также  
 [Using CStringT](../atl-mfc-shared/using-cstringt.md)   
 [Using CString](../atl-mfc-shared/using-cstring.md)