---
title: /CLRSUPPORTLASTERROR (Сохранение кода последней ошибки для вызовов PInvoke)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 19930591c2d0406c68b1a408622a49c9e8b1d551
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322277"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (Сохранение кода последней ошибки для вызовов PInvoke)

**/CLRSUPPORTLASTERROR**, который находится на по умолчанию, сохраняет последний код ошибки функций, вызванных через p/ Invoke механизм, который позволяет вызывать родные функции в DLLS, из кода, компилированного с **/clr**.

## <a name="syntax"></a>Синтаксис

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Remarks

Сохранение последнего кода ошибки означает снижение производительности.  Если вы не хотите, чтобы нести влияние на производительность сохранения последнего кода ошибки, ссылка с **/CLRSUPPORTLASTERROR:NO**.

Вы можете свести к минимуму влияние на производительность, связавшись с **/CLRSUPPORTLASTERROR:SYSTEMDLL**, который сохраняет только последний код ошибки для функций в системе DLLs.  Система DLL определяется как одна из следующих:

|||||
|-|-|-|-|
|ACLUI. Dll|АКТИВДС. Dll|АДПТИФ. Dll|ADVAPI32. Dll|
|АСИКФИЛТ. Dll|АУТХЗ. Dll|AVICAP32. Dll|AVIFIL32. Dll|
|Кабинет. Dll|CLUSAPI. Dll|COMCTL32. Dll|COMDLG32. Dll|
|КОМСВЦ. Dll|КРЕДУИ. Dll|CRYPT32. Dll|КРИПТНЕТ. Dll|
|КРИПТУИ. Dll|D3D8THK. Dll|DBGENG. Dll|DBGHELP. Dll|
|DCIMAN32. Dll|DNSAPI. Dll|DSPROP. Dll|ДГУИЕКСТ. Dll|
|GDI32. Dll|GLU32. Dll|HLINK. Dll|ICM32. Dll|
|IMAGEHLP. Dll|IMM32. Dll|IPHLPAPI. Dll|ИПРОП. Dll|
|ЯДРО32. Dll|КСУЗЕР. Dll|LOADPERF. Dll|L-32. Dll|
|MAPI32. Dll|MGMTAPI. Dll|МОБСИН. Dll|Mpr. Dll|
|МРАППИ. Dll|МЗРТ. Dll|MSACM32. Dll|MSCMS. Dll|
|Msi. Dll|MSIMG32. Dll|MSRATING. Dll|МСТАЧ. Dll|
|MSVFW32. Dll|МСВОСОК. Dll|MTXEX. Dll|НДДЕАПИ. Dll|
|NETAPI32. Dll|АЭСБУРМС. Dll|NTDSAPI. Dll|NTDSBCLI. Dll|
|NTMSAPI. Dll|ODBC32. Dll|ODBCBCP. Dll|OLE32. Dll|
|ОЛЕАКС. Dll|OLEAUT32. Dll|ОЛЕДЛГ. Dll|OPENGL32. Dll|
|Pdh. Dll|ПОВПРОФ. Dll|ЗОСНАМЕ. Dll|Запроса. Dll|
|RASAPI32. Dll|РАСДЛГ. Dll|РАССАПИ. Dll|РЕСУТИЛС. Dll|
|RICHED20. Dll|RPCNS4. Dll|RPCRT4. Dll|Rtm. Dll|
|ЛЕТТИЛС. Dll|СКАРДЛГ. Dll|SECUR32. Dll|SENSAPI. Dll|
|SETUPAPI. Dll|Sfc. Dll|Shell32. Dll|SHFOLDER. Dll|
|SHLWAPI. Dll|SISBKUP. Dll|SNMPAPI. Dll|СРЛИНЕС. Dll|
|Иппп. Dll|TAPI32. Dll|Трафика. Dll|Url. Dll|
|УРЛМОН. Dll|USER32. Dll|Userenv. Dll|USP10. Dll|
|UXTHEME. Dll|VDMDBG. Dll|Версия. Dll|Winfax. Dll|
|ВАЙНХHTTP. Dll|Wininet. Dll|ВИНММ. Dll|WINSCARD. Dll|
|WINTRUST. Dll|WLDAP32. Dll|WOW32. Dll|WS2_32.DLL|
|WSNMP32. Dll|WSOCK32.DLL|ВЦКАПИ32. Dll|XOLEHLP. Dll|

> [!NOTE]
> Сохранение последней ошибки не поддерживается для неуправляемых функций, которые потребляются кодом CLR, в том же модуле.

- Для получения дополнительной информации [см.](clr-common-language-runtime-compilation.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Выберите папку **компоновщика**.

1. Выберите страницу свойств **Командная строка** .

1. Введите опцию в поле **дополнительных опций.**

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="example"></a>Пример

Следующий пример определяет родной DLL с одной экспортируемой функцией, которая изменяет последнюю ошибку.

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

Следующий образец потребляет DLL, демонстрируя, как использовать **/CLRSUPPORTLASTERROR**.

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

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Варианты MSVC Linker](linker-options.md)
