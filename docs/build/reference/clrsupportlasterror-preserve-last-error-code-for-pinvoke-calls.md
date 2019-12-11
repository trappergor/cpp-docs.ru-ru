---
title: /CLRSUPPORTLASTERROR (Сохранение кода последней ошибки для вызовов PInvoke)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 64948d81759d415245e741bc6152d56bb35480d2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988350"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (Сохранение кода последней ошибки для вызовов PInvoke)

**Параметр/CLRSUPPORTLASTERROR**, который включен по умолчанию, сохраняет последний код ошибки функций, вызываемых через механизм P/Invoke, который позволяет вызывать собственные функции в библиотеках DLL из кода, скомпилированного с **параметром/CLR**.

## <a name="syntax"></a>Синтаксис

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Заметки

Сохранение последнего кода ошибки подразумевает снижение производительности.  Если вы не хотите повлиять на производительность с сохранением последнего кода ошибки, выполните компоновку с помощью **параметр/CLRSUPPORTLASTERROR: No**.

Можно уменьшить влияние на производительность, связавсь с **параметр/CLRSUPPORTLASTERROR: системдлл**, который сохраняет только последний код ошибки для функций в системных библиотеках DLL.  Системная библиотека DLL определяется как одно из следующих:

|||||
|-|-|-|-|
|АКЛУИ. КОМПОНОВКИ|АКТИВЕДС. КОМПОНОВКИ|АДПТИФ. КОМПОНОВКИ|ADVAPI32.DLL|
|АСИКФИЛТ. КОМПОНОВКИ|Авторизации. КОМПОНОВКИ|AVICAP32.DLL|AVIFIL32. КОМПОНОВКИ|
|Файле. КОМПОНОВКИ|КЛУСАПИ. КОМПОНОВКИ|COMCTL32.DLL|COMDLG32. КОМПОНОВКИ|
|КОМСВКС. КОМПОНОВКИ|CREDUI. КОМПОНОВКИ|CRYPT32.DLL|КРИПТНЕТ. КОМПОНОВКИ|
|Динамической компоновки Cryptui. КОМПОНОВКИ|D3D8THK. КОМПОНОВКИ|DBGENG. КОМПОНОВКИ|DBGHELP. КОМПОНОВКИ|
|DCIMAN32. КОМПОНОВКИ|ДНСАПИ. КОМПОНОВКИ|ДСПРОП. КОМПОНОВКИ|ДСУИЕКСТ. КОМПОНОВКИ|
|GDI32. КОМПОНОВКИ|GLU32. КОМПОНОВКИ|Библиотеке. КОМПОНОВКИ|ICM32. КОМПОНОВКИ|
|Imagehlp. КОМПОНОВКИ|IMM32. КОМПОНОВКИ|ИФЛПАПИ. КОМПОНОВКИ|ИПРОП. КОМПОНОВКИ|
|Kernel32. КОМПОНОВКИ|КСУСЕР. КОМПОНОВКИ|LOADPERF. КОМПОНОВКИ|LZ32. КОМПОНОВКИ|
|Библиотека MAPI32. КОМПОНОВКИ|МГМТАПИ. КОМПОНОВКИ|МОБСИНК. КОМПОНОВКИ|MPR. КОМПОНОВКИ|
|МПРАПИ. КОМПОНОВКИ|МКРТ. КОМПОНОВКИ|MSACM32. КОМПОНОВКИ|МСКМС. КОМПОНОВКИ|
|MSI. КОМПОНОВКИ|MSIMG32. КОМПОНОВКИ|МСРАТИНГ. КОМПОНОВКИ|МСТАСК. КОМПОНОВКИ|
|MSVFW32. КОМПОНОВКИ|МСВСОКК. КОМПОНОВКИ|МТКСЕКС. КОМПОНОВКИ|НДДЕАПИ. КОМПОНОВКИ|
|NETAPI32. КОМПОНОВКИ|НППТУЛС. КОМПОНОВКИ|NTDSAPI. КОМПОНОВКИ|NTDSBCLI.DLL|
|НТМСАПИ. КОМПОНОВКИ|Библиотеками odbc32. КОМПОНОВКИ|ODBCBCP. КОМПОНОВКИ|Ole32. КОМПОНОВКИ|
|ОЛЕАКК. КОМПОНОВКИ|Oleaut32. КОМПОНОВКИ|ОЛЕДЛГ. КОМПОНОВКИ|OPENGL32. КОМПОНОВКИ|
|PDH. КОМПОНОВКИ|ПОВРПРОФ. КОМПОНОВКИ|КОСНАМЕ. КОМПОНОВКИ|Выбор. КОМПОНОВКИ|
|RASAPI32.DLL|РАСДЛГ. КОМПОНОВКИ|РАССАПИ. КОМПОНОВКИ|РЕСУТИЛС. КОМПОНОВКИ|
|Библиотеки RICHED20. КОМПОНОВКИ|RPCNS4. КОМПОНОВКИ|RPCRT4. КОМПОНОВКИ|RTM. КОМПОНОВКИ|
|РТУТИЛС. КОМПОНОВКИ|СКАРДДЛГ. КОМПОНОВКИ|SECUR32. КОМПОНОВКИ|СЕНСАПИ. КОМПОНОВКИ|
|Setupapi. КОМПОНОВКИ|SFC. КОМПОНОВКИ|Библиотеки. КОМПОНОВКИ|ШФОЛДЕР. КОМПОНОВКИ|
|SHLWAPI.DLL|СИСБКУП. КОМПОНОВКИ|СНМПАПИ. КОМПОНОВКИ|СРКЛИЕНТ. КОМПОНОВКИ|
|СТИ. КОМПОНОВКИ|TAPI32. КОМПОНОВКИ|Трафика. КОМПОНОВКИ|URL-адрес. КОМПОНОВКИ|
|Urlmon. КОМПОНОВКИ|User32. КОМПОНОВКИ|Следующая. КОМПОНОВКИ|USP10. КОМПОНОВКИ|
|УКССЕМЕ. КОМПОНОВКИ|ВДМДБГ. КОМПОНОВКИ|Версия. КОМПОНОВКИ|ВИНФАКС. КОМПОНОВКИ|
|Известен. КОМПОНОВКИ|Операционной. КОМПОНОВКИ|WINMM. КОМПОНОВКИ|WINSCARD. КОМПОНОВКИ|
|ВИНТРУСТ. КОМПОНОВКИ|WLDAP32. КОМПОНОВКИ|WOW32. КОМПОНОВКИ|WS2_32. DLL|
|WSNMP32. КОМПОНОВКИ|WSOCK32.DLL|WTSAPI32. КОМПОНОВКИ|КСОЛЕХЛП. КОМПОНОВКИ|

> [!NOTE]
>  Сохранение последней ошибки не поддерживается для неуправляемых функций, используемых кодом CLR в одном модуле.

- Дополнительные сведения см. в разделе [/clr (компиляция CLR)](clr-common-language-runtime-compilation.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в поле **Дополнительные параметры** .

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="example"></a>Пример

В следующем примере определяется собственная библиотека DLL с одной экспортированной функцией, которая изменяет последнюю ошибку.

```cpp
// CLRSUPPORTLASTERROR_dll.cpp
// compile with: /LD
#include <windows.h>
#include <math.h>

#pragma unmanaged
__declspec(dllexport) double MySqrt(__int64 n) {
   SetLastError(DWORD(-1));
   return sqrt(double(n));
}
```

## <a name="example"></a>Пример

В следующем примере используется библиотека DLL, в которой демонстрируется использование **параметр/CLRSUPPORTLASTERROR**.

```cpp
// CLRSUPPORTLASTERROR_client.cpp
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll
// processor: x86
#include <windows.h>
#include <wininet.h>
#include <stdio.h>
#include <math.h>

#pragma comment(lib, "wininet.lib")

double MySqrt(__int64 n);

#pragma managed
int main() {
   double   d = 0.0;
   __int64 n = 65;
   HANDLE  hGroup = NULL;
   GROUPID groupID;
   DWORD   dwSet = 127, dwGet = 37;

   SetLastError(dwSet);
   d = MySqrt(n);
   dwGet = GetLastError();

   if (dwGet == DWORD(-1))
      printf_s("GetLastError for application call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for application call failed (%d).\n",
             dwGet);

   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,
                           0, 0, &groupID, 0);
   dwGet = GetLastError();
   if (dwGet == 183)
      printf_s("GetLastError for system call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for system call failed (%d).\n",
             dwGet);
}
```

```Output
GetLastError for application call failed (127).
GetLastError for system call succeeded (183).
```

## <a name="see-also"></a>См. также:

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
