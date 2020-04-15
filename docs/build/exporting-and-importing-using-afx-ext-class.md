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
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328600"
---
# <a name="exporting-and-importing-using-afx_ext_class"></a>Экспортирование и импортирование с использованием AFX_EXT_CLASS

[DLL расширения MFC](extension-dlls-overview.md) используют **макроAFX_EXT_CLASS** для экспорта классов; исполнители, которые ссылаются на расширение MFC DLL, используют макрос для классов импорта. С **AFX_EXT_CLASS** макроса, те же файлы заголовка, которые используются для создания DLL расширения MFC, могут быть использованы с исполнителями, которые ссылаются на DLL.

В файл заголовка для DLL добавьте **ключевое** слово AFX_EXT_CLASS в декларацию вашего класса следующим образом:

```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
```

Этот макрос определяется `__declspec(dllexport)` MFC как `_AFXDLL` при `_AFXEXT` предварительном процессоре символов и определены. Но макрос определяется как `__declspec(dllimport)` когда `_AFXDLL` определяется и `_AFXEXT` не определяется. При определении предпроцессорный символ `_AFXDLL` указывает, что общая версия MFC используется используемой целевой (либо DLL, либо приложением). При `_AFXDLL` определении обоих и `_AFXEXT` определении указывается, что целью является расширение MFC DLL.

Поскольку `AFX_EXT_CLASS` при `__declspec(dllexport)` экспорте из DLL расширения MFC можно экспортировать целые классы, не размещая в файле .def оформленные имена для всех символов этого класса.

Хотя вы можете избежать создания файла .def и всех украшенных имен для класса с помощью этого метода, создание файла .def является более эффективным, поскольку имена могут быть экспортированы по обычному. Чтобы использовать метод экспорта файла .def, поместите следующий код в начале и конце файла заголовка:

```cpp
#undef AFX_DATA
#define AFX_DATA AFX_EXT_DATA
// <body of your header file>
#undef AFX_DATA
#define AFX_DATA
```

> [!CAUTION]
> Будьте осторожны при экспорте внеочередных функций, так как они могут создавать возможность конфликтов версий. Вневливая функция расширяется в код приложения; поэтому, если позже переписать функцию, она не будет обновлена, если само приложение не будет перекомпилировано. Как правило, функции DLL могут обновляться без восстановления приложений, которые их используют.

## <a name="exporting-individual-members-in-a-class"></a>Экспорт отдельных членов в классе

Иногда вы можете экспортировать отдельных членов вашего класса. Например, если вы экспортируете класс `CDialog`,derived, возможно, потребуется `DoModal` экспортировать конструктор и вызов. Вы можете `AFX_EXT_CLASS` использовать на отдельных членов вам нужно экспортировать.

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

Поскольку вы больше не экспортируете всех членов класса, вы можете столкнуться с дополнительной проблемой из-за того, как работают макросы MFC. Некоторые из макросов-помощников MFC фактически декларируют или определяют данные. Таким образом, эти данные также должны быть экспортированы из вашего DLL.

Например, `DECLARE_DYNAMIC` макрос определяется следующим образом при создании DLL расширения MFC:

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
   static CRuntimeClass* PASCAL _GetBaseClass(); \
public: \
   static AFX_DATA CRuntimeClass class##class_name; \
   virtual CRuntimeClass* GetRuntimeClass() const; \
```

Линия, которая начинается со статического, `AFX_DATA` объявляет статический объект внутри вашего класса. Чтобы правильно экспортировать этот класс и получить доступ к информации о времени выполнения от клиента, вы должны экспортировать этот статический объект. Поскольку статический объект объявляется `AFX_DATA`с помощью `AFX_DATA` модификатора, необходимо только определить, чтобы быть `__declspec(dllexport)` при создании DLL и определить его как `__declspec(dllimport)` при создании вашего клиента исполняемых. Поскольку `AFX_EXT_CLASS` уже определено таким образом, вам `AFX_DATA` просто нужно `AFX_EXT_CLASS` переопределить, чтобы быть таким же, как вокруг определения класса.

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

Поскольку MFC `AFX_DATA` всегда использует символ на элементах данных, которые он определяет в своих макросах, этот метод работает для всех таких сценариев. Например, он `DECLARE_MESSAGE_MAP`работает для .

> [!NOTE]
> Если вы экспортируете весь класс, а не выбранные члены класса, статические участники данных автоматически экспортируются.

### <a name="what-do-you-want-to-do"></a>Выбор действия

- [Экспорт из DLL с использованием файлов .def](exporting-from-a-dll-using-def-files.md)

- [Экспорт из DLL с использованием __declspec (dllexport)](exporting-from-a-dll-using-declspec-dllexport.md)

- [Экспортные функции СЗЗ для использования в исполнителях C-языка](exporting-cpp-functions-for-use-in-c-language-executables.md)

- [Функции экспорта C для использования в исполнителях C или C-языка](exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)

- [Определение подходящего способа экспорта](determining-which-exporting-method-to-use.md)

- [Импорт в приложение с помощью __declspec(dllimport)](importing-into-an-application-using-declspec-dllimport.md)

- [Инициализация DLL](run-time-library-behavior.md#initializing-a-dll)

### <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Внутренние имена](reference/decorated-names.md)

- [Импорт и экспорт встраиваемых функций](importing-and-exporting-inline-functions.md)

- [Взаимный импорт](mutual-imports.md)

## <a name="see-also"></a>См. также раздел

[Экспорт из библиотеки DLL](exporting-from-a-dll.md)
