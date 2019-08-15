---
title: GetProcAddress
ms.date: 11/04/2016
f1_keywords:
- GetProcAddress
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
ms.openlocfilehash: 2d322cfe7d3bd60d8d702a226e181eb7b4ede963
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493250"
---
# <a name="getprocaddress"></a>GetProcAddress

Процессы, явно связываемые с библиотекой DLL, вызывают [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) для получения адреса экспортированной функции в библиотеке DLL. Для вызова функции DLL используется указатель на возвращаемую функцию. **GetProcAddress** принимает в качестве параметров обработчик DLL-модуля (возвращаемыйс помощью `AfxLoadLibrary`LoadLibrary, или **Ошибка GetModuleHandle**) и принимает либо имя функции, которую требуется вызвать, либо порядковый номер экспорта функции.

Так как вы вызываете функцию DLL с помощью указателя и не выполняете проверку типов во время компиляции, убедитесь, что параметры функции верны, чтобы не переделать память, выделенную в стеке, и вызвать нарушение прав доступа. Одним из способов обеспечения безопасности типов является просмотр прототипов функций экспортированных функций и создание соответствующих typedef для указателей на функции. Например:

```
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);
...

HINSTANCE hDLL;               // Handle to DLL
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
DWORD dwParam1;
UINT  uParam2, uReturnVal;

hDLL = LoadLibrary("MyDLL");
if (hDLL != NULL)
{
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,
                                           "DLLFunc1");
   if (!lpfnDllFunc1)
   {
      // handle the error
      FreeLibrary(hDLL);
      return SOME_ERROR_CODE;
   }
   else
   {
      // call the function
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);
   }
}
```

Указание требуемой функции при вызове **GetProcAddress** зависит от способа построения библиотеки DLL.

Порядковый номер экспорта можно получить только в том случае, если библиотека DLL, с которой выполняется связывание, построена с помощью файла определения модуля (DEF) и если порядковые номера указаны с помощью функций в разделе " **Экспорт** " DEF-файла библиотеки DLL. Вызов **GetProcAddress** с порядковым номером экспорта, в отличие от имени функции, выполняется несколько быстрее, если в библиотеке DLL содержится много экспортированных функций, поскольку порядковые номера экспорта служат в качестве индексов в таблице экспорта DLL. При использовании порядкового номера экспорта **GetProcAddress** может напрямую наыскать функцию, в отличие от сравнения указанного имени с именами функций в таблице экспорта библиотеки DLL. Однако вызов **GetProcAddress** с порядком экспорта следует выполнять только в том случае, если вы контролируете назначение порядковым номерам экспортируемых функций в DEF файле.

## <a name="what-do-you-want-to-do"></a>Выберите действие

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#linking-implicitly)

- [Связывание исполняемого файла с библиотекой DLL](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Функции LoadLibrary и AfxLoadLibrary](loadlibrary-and-afxloadlibrary.md)

- [FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)

- [Экспорт из библиотеки DLL с использованием DEF-файлов](exporting-from-a-dll-using-def-files.md)

## <a name="see-also"></a>См. также

[Создание библиотек DLL C/C++ в Visual Studio](dlls-in-visual-cpp.md)
