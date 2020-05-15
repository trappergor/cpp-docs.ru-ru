---
title: Экспортирование и импортирование с использованием AFX_EXT_CLASS
ms.date: 11/04/2016
f1_keywords:
- afx_ext_class
helpviewer_keywords:
- AFX_EXT_CLASS macro
- exporting classes [C++]
- importing DLLs [C++]
- extension DLLs [C++], exporting classes
- executable files [C++], importing classes
- exporting DLLs [C++], AFX_EXT_CLASS macro
ms.assetid: 6b72cb2b-e92e-4ecd-bcab-c335e1d1cfde
ms.openlocfilehash: 95c72f8251a8a59833483eb948709c80a69d03d7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328600"
---
# <a name="exporting-and-importing-using-afx_ext_class"></a>Экспортирование и импортирование с использованием AFX_EXT_CLASS

[Библиотеки DLL расширения MFC](extension-dlls-overview.md) используют макрос **AFX_EXT_CLASS** для экспорта классов; исполняемые файлы, которые связываются с библиотекой DLL расширения MFC, используют макрос для импорта классов. При использовании макроса **AFX_EXT_CLASS** те же файлы заголовков, которые используются для сборки библиотеки DLL расширения MFC, можно использовать с исполняемыми файлами, которые связываются с библиотекой DLL.

В файле заголовка для библиотеки DLL добавьте ключевое слово **AFX_EXT_CLASS** в объявление класса следующим образом:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Этот макрос определяется MFC как `__declspec(dllexport)`, если определены символы препроцессора `_AFXDLL` и `_AFXEXT`. Но макрос определяется как `__declspec(dllimport)`, если `_AFXDLL` определен, а `_AFXEXT` не определен. Если определен, символ препроцессора `_AFXDLL` указывает, что общая версия MFC используется целевым исполняемым объектом (библиотекой DLL или приложением). Если определены и `_AFXDLL`, и `_AFXEXT`, это означает, что целевой исполняемый файл является библиотекой DLL расширения MFC.

Поскольку при экспорте из библиотеки DLL расширения MFC `AFX_EXT_CLASS` определяется как `__declspec(dllexport)`, можно экспортировать целые классы без добавления внутренних имен для всех символов этого класса в DEF-файле.

Хотя можно не создавать DEF-файл и все внутренние имена класса с помощью этого метода, создание DEF-файла является более эффективным способом, так как имена можно экспортировать по порядковому номеру. Чтобы использовать метод экспорта с применением DEF-файла, поместите следующий код в начало и в конец файла заголовка:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
> Будьте внимательны при экспорте встроенных функций, поскольку они могут создать вероятность конфликтов версий. Встроенная функция расширяется в код приложения; поэтому при последующей перезаписи функции она не обновляется, пока не будет перекомпилировано само приложение. Как правило, функции DLL могут обновляться без перестроения приложений, которые их используют.

## <a name="exporting-individual-members-in-a-class"></a>Экспорт отдельных элементов в классе

Иногда может потребоваться экспортировать отдельные элементы класса. Например, при экспорте класса, производного от `CDialog`, может потребоваться экспортировать только конструктор и вызов `DoModal`. Можно использовать `AFX_EXT_CLASS` для отдельных элементов, которые необходимо экспортировать.

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

Поскольку вы не экспортируете все элементы класса, можно столкнуться с дополнительными проблемами из-за способа работы макросов MFC. Некоторые из вспомогательных макросов MFC объявляют или определяют элементы данных. Поэтому эти элементы данных также следует экспортировать из библиотеки DLL.

Например, макрос `DECLARE_DYNAMIC` определяется следующим образом при сборке библиотеки DLL расширения MFC.

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Строка, которая начинается со статического `AFX_DATA`, объявляет статический объект внутри класса. Чтобы правильно экспортировать этот класс и получить доступ к сведениям среды выполнения из исполняемого файла клиента, необходимо экспортировать этот статический объект. Поскольку статический объект объявляется с модификатором `AFX_DATA`, необходимо определить только `AFX_DATA` как `__declspec(dllexport)` при сборке библиотеки DLL и определить ее как `__declspec(dllimport)` при сборке исполняемого файла клиента. Поскольку `AFX_EXT_CLASS` уже определен таким образом, необходимо лишь переопределить `AFX_DATA`, чтобы они совпадали с `AFX_EXT_CLASS` из определения класса.

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

Поскольку MFC всегда использует символ `AFX_DATA` для элементов данных, которые он определяет в макросах, этот метод работает для всех таких сценариев. Например, он работает для `DECLARE_MESSAGE_MAP`.

> [!NOTE]
> При экспорте всего класса вместо отдельных элементов класса статические элементы данных экспортируются автоматически.

### <a name="what-do-you-want-to-do"></a>Выберите действие

- [Экспорт из библиотеки DLL с использованием DEF-файлов](exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт функций на языке C++ для использования в исполняемых модулях, исходный код которых написан на языке C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Экспорт функций на языке C для использования в исполняемых файлах, исходный код которых написан на языке C или C++](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Внутренние имена](reference/decorated-names.md)

- [Импорт и экспорт встраиваемых функций](importing-and-exporting-inline-functions.md)

- [Взаимный импорт](mutual-imports.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
