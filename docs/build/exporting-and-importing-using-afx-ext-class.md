---
title: "Экспортирование и импортирование с использованием AFX_EXT_CLASS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afx_ext_class
dev_langs:
- C++
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb47703b7cd4ef2d0493016c120db0b7d845a71f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-and-importing-using-afxextclass"></a>Экспортирование и импортирование с использованием AFX_EXT_CLASS  
  
[Библиотека DLL-расширения MFC](../build/extension-dlls-overview.md) используйте макрос **AFX_EXT_CLASS** Экспорт классов; исполняемые файлы, связанные с DLL расширений MFC использовать макрос для импорта классы. С **AFX_EXT_CLASS** макрос, файл заголовка, используемые для построения расширения MFC DLL может использоваться с исполняемыми файлами, связан с библиотекой DLL.  
  
 Добавьте в файл заголовка для библиотеки DLL, **AFX_EXT_CLASS** ключевое слово в объявление класса следующим образом:  
  
```cpp  
class AFX_EXT_CLASS CMyClass : public CDocument  
{  
// <body of class>  
};  
```  
  
Этот макрос определяется MFC как `__declspec(dllexport)` при символы препроцессора `_AFXDLL` и `_AFXEXT` определены. Однако макрос определен как `__declspec(dllimport)` при `_AFXDLL` определяется и `_AFXEXT` не определен. Если определен символ препроцессора `_AFXDLL` указывает, что общая версия MFC используется целевой исполняемый файл (DLL или приложения). Если оба `_AFXDLL` и `_AFXEXT` являются определен, это означает, что целевой исполняемый файл является Библиотекой расширения MFC.  
  
Поскольку `AFX_EXT_CLASS` определяется как `__declspec(dllexport)` экспорта данных из библиотеки DLL расширения MFC, можно экспортировать все классы без помещения в DEF-файл декорированные имена для всех символов этого класса.  
  
Несмотря на то, что можно избежать создания DEF-файла и всех декорированных имен для класса с помощью этого метода, является более эффективным DEF-файл, так как имена могут быть экспортированы по порядковому номеру. Чтобы использовать метод файл .def экспорта, поместите следующий код в начале и в конце файла заголовка:  
  
```cpp  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
> [!CAUTION]
>  Будьте внимательны при Экспорт встроенных функций, поскольку они могут вызвать конфликты версий. Встроенная функция разворачивается в код приложения; Таким образом Если функция написан позже, оно обновится, если не перекомпилируется самого приложения. Как правило функции DLL можно обновить без повторного построения приложений, которые их используют.  
  
## <a name="exporting-individual-members-in-a-class"></a>Экспортирование отдельных членов в классе  
  
Иногда может потребоваться экспортирования отдельных членов класса. Например, если вы экспортируете `CDialog`-производного класса может потребоваться только для экспорта в конструктор и `DoModal` вызова. Можно использовать `AFX_EXT_CLASS` для отдельных членов, которые требуется экспортировать.  
  
Пример:  
  
```cpp  
class CExampleDialog : public CDialog  
{  
public:  
   AFX_EXT_CLASS CExampleDialog();  
   AFX_EXT_CLASS int DoModal();  
   ...  
   // rest of class definition  
   ...  
};  
```  
  
Поскольку все члены класса больше не экспортируются, вы можете столкнуться дополнительную проблему из-за способа работы макросов библиотеки MFC. Несколько вспомогательных макросов MFC объявляют или определяют члены данных. Таким образом эти члены данных также должны быть экспортированы из библиотеки DLL.  
  
Например `DECLARE_DYNAMIC` при создании библиотеки DLL расширения MFC макрос определяется следующим образом:  
  
```cpp  
#define DECLARE_DYNAMIC(class_name) \  
protected: \  
   static CRuntimeClass* PASCAL _GetBaseClass(); \  
public: \  
   static AFX_DATA CRuntimeClass class##class_name; \  
   virtual CRuntimeClass* GetRuntimeClass() const; \  
```  
  
Строка, которая начинается с статической `AFX_DATA` , объявляет статический объект внутри класса. Чтобы правильно экспортировать класс и доступа к данным во время выполнения из исполняемый файл клиента, необходимо экспортировать статический объект. Так как статический объект объявлен с модификатором `AFX_DATA`, необходимо определить `AFX_DATA` быть `__declspec(dllexport)` при построении библиотеки DLL, а также определить как `__declspec(dllimport)` при построении исполняемый файл клиента. Поскольку `AFX_EXT_CLASS` уже определен таким образом, необходимо переопределить `AFX_DATA` же `AFX_EXT_CLASS` вокруг его определение.  
  
Пример:  
  
```cpp  
#undef  AFX_DATA  
#define AFX_DATA AFX_EXT_CLASS  
  
class CExampleView : public CView  
{  
   DECLARE_DYNAMIC()  
   // ... class definition ...  
};  
  
#undef  AFX_DATA  
#define AFX_DATA  
```  
  
Поскольку MFC всегда использует `AFX_DATA` символов для элементов данных, он определяет в пределах своего макроса, эта технология работает для всех подобных скриптов. Например, он работает для `DECLARE_MESSAGE_MAP`.  
  
> [!NOTE]
>  Если экспортируется весь класс, а не выбранные члены класса, статические члены данных экспортируются автоматически.  
  
### <a name="what-do-you-want-to-do"></a>Выберите действие  
  
-   [Экспорт из библиотеки DLL с использованием DEF-файлы](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Экспорт из библиотеки DLL с помощью __declspec(dllexport)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Экспорт функций C++ для использования в реализации языка C](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Выбор подходящего метода экспорта для использования](../build/determining-which-exporting-method-to-use.md)  
  
-   [Импорт в приложение с помощью __declspec(dllimport)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Инициализация библиотеки DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
  
-   [Внутренние имена](../build/reference/decorated-names.md)  
  
-   [Импорт и экспорт встроенных функций](../build/importing-and-exporting-inline-functions.md)  
  
-   [Взаимный импорт](../build/mutual-imports.md)  
  
## <a name="see-also"></a>См. также  
 [Экспорт из библиотеки DLL](../build/exporting-from-a-dll.md)