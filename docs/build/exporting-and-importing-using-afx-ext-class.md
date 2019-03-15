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
ms.openlocfilehash: bcfdc94e8db80daec227d77c20ecec6b14d5af11
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821226"
---
# <a name="exporting-and-importing-using-afxextclass"></a>Экспортирование и импортирование с использованием AFX_EXT_CLASS

[Библиотеки DLL расширений MFC](extension-dlls-overview.md) используйте макрос **AFX_EXT_CLASS** Экспорт классов; исполняемые файлы, связанные библиотеки DLL расширения MFC использовать макрос для импорта классов. С помощью **AFX_EXT_CLASS** макрос, тех же файлов заголовков, которые используются для построения библиотеки DLL, которые могут использоваться с исполняемыми файлами, связанных с библиотекой DLL расширения MFC.

Добавьте в файл заголовка для библиотеки DLL, **AFX_EXT_CLASS** ключевое слово в объявление класса следующим образом:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Этот макрос определяется MFC как `__declspec(dllexport)` при символы препроцессора `_AFXDLL` и `_AFXEXT` определены. Но макрос определяется как `__declspec(dllimport)` при `_AFXDLL` определен и `_AFXEXT` не определен. Если определен символ препроцессора `_AFXDLL` указывает, что используется общей версии MFC, целевой исполняемый файл (библиотеки DLL или приложения). Когда оба `_AFXDLL` и `_AFXEXT` будут определены, это означает, что целевой исполняемый файл — это библиотеки DLL расширения MFC.

Так как `AFX_EXT_CLASS` определяется как `__declspec(dllexport)` при экспорте из библиотеки DLL расширения MFC, не помещая декорированные имена для всех символов этого класса в DEF-файл можно экспортировать целых классов.

Несмотря на то, что можно избежать создания DEF-файла и всех декорированных имен для класса с помощью этого метода, является более эффективным DEF-файл, так как имена могут быть экспортированы по порядковому номеру. Чтобы использовать метод файл .def экспорта, поместите следующий код в начале и конце файла заголовка:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
>  Будьте внимательны при Экспорт встраиваемых функций, так как они могут вызвать конфликты версий. Встроенная функция разворачивается в код приложения; Таким образом Если позже вы повторное написание функции, она не обновится, если не перекомпилируется само приложение. Как правило функции DLL могут обновляться без повторной сборки приложения, которые их используют.

## <a name="exporting-individual-members-in-a-class"></a>Экспортирование отдельных членов в классе

Иногда требуется экспортировать отдельные члены класса. Например, если при экспорте `CDialog`-производного класса только необходимо экспортировать в конструктор и `DoModal` вызова. Можно использовать `AFX_EXT_CLASS` для отдельных членов, нужно экспортировать.

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

Так как больше не экспортируются все члены класса, вы можете столкнуться дополнительную проблему из-за способа работы макросов библиотеки MFC. Несколько вспомогательных макросов MFC объявляют или определяют члены данных. Таким образом эти данные-члены также должны экспортироваться из библиотеки DLL.

Например `DECLARE_DYNAMIC` при построении библиотеки DLL расширения MFC макрос определяется следующим образом:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Строка, которая начинается с статической `AFX_DATA` объявляет статический объект внутри класса. Для успешного выполнения экспорта этого класса и применения данных времени выполнения из исполняемый файл клиента, необходимо экспортировать статический объект. Так как статический объект объявлен с модификатором `AFX_DATA`, необходимо определить `AFX_DATA` быть `__declspec(dllexport)` при построении библиотеки DLL и определяют его как `__declspec(dllimport)` при построении исполняемый файл клиента. Так как `AFX_EXT_CLASS` уже определен в этом случае нужно переопределить `AFX_DATA` быть так же, как `AFX_EXT_CLASS` вокруг его определение.

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

Поскольку MFC всегда использует `AFX_DATA` символов для элементов данных, он определяет в пределах своего макроса, эта технология работает для всех подобных скриптов. Например, она работает для `DECLARE_MESSAGE_MAP`.

> [!NOTE]
>  Если экспортируется весь класс, а не выбранные элементы класса, автоматически экспортируются статические данные-члены.

### <a name="what-do-you-want-to-do"></a>Выберите действие.

- [Экспорт из DLL с использованием DEF-файлы](exporting-from-a-dll-using-def-files.md)

- [Экспорт из библиотеки DLL с использованием __declspec(dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспорт функций C++ для использования в исполняемых файлах языка C](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Экспорт функций на языке C для использования в исполняемых файлах C или C++-язык](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего метода экспорта для использования](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация библиотеки DLL](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Декорированные имена](reference/decorated-names.md)

- [Импорт и экспорт встраиваемых функций](importing-and-exporting-inline-functions.md)

- [Взаимный импорт](mutual-imports.md)

## <a name="see-also"></a>См. также

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
