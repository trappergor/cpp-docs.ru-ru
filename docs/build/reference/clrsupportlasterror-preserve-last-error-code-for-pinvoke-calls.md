---
title: /CLRSUPPORTLASTERROR (Сохранение кода последней ошибки для вызовов PInvoke)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: e813966367b4349a95c174c59340204592b81b74
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660922"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (Сохранение кода последней ошибки для вызовов PInvoke)

**/ CLRSUPPORTLASTERROR**, включенном по умолчанию, сохраняет последний код ошибки функций вызывать с помощью механизма P/Invoke, который позволяет вызывать собственных функций в библиотеках DLL, из кода компилируется с **/CLR**.

## <a name="syntax"></a>Синтаксис

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Примечания

Сохранение кода последней ошибки подразумевает снижение производительности.  Если вы не хотите снижать производительность сохранения последний код ошибки, связать с **/CLRSUPPORTLASTERROR:NO**.

Можно свести к минимуму влияние на производительность путем связывания с **/CLRSUPPORTLASTERROR:SYSTEMDLL**, который сохраняет только последний код ошибки для функций в системных библиотек DLL.  Системных DLL определяется как один из следующих:

|||||
|-|-|-|-|
|УСОВЕРШЕНСТВОВАННЫЙ. БИБЛИОТЕКИ DLL|ACTIVEDS. БИБЛИОТЕКИ DLL|ADPTIF. БИБЛИОТЕКИ DLL|ADVAPI32. БИБЛИОТЕКИ DLL|
|ASYCFILT. БИБЛИОТЕКИ DLL|AUTHZ. БИБЛИОТЕКИ DLL|AVICAP32. БИБЛИОТЕКИ DLL|AVIFIL32. БИБЛИОТЕКИ DLL|
|CAB-ФАЙЛ. БИБЛИОТЕКИ DLL|CLUSAPI. БИБЛИОТЕКИ DLL|COMCTL32. БИБЛИОТЕКИ DLL|COMDLG32. БИБЛИОТЕКИ DLL|
|COMSVCS. БИБЛИОТЕКИ DLL|CREDUI. БИБЛИОТЕКИ DLL|ФУНКЦИЯ CRYPT32. БИБЛИОТЕКИ DLL|CRYPTNET. БИБЛИОТЕКИ DLL|
|CRYPTUI. БИБЛИОТЕКИ DLL|D3D8THK. БИБЛИОТЕКИ DLL|DBGENG. БИБЛИОТЕКИ DLL|DBGHELP. БИБЛИОТЕКИ DLL|
|DCIMAN32. БИБЛИОТЕКИ DLL|DNSAPI. БИБЛИОТЕКИ DLL|DSPROP. БИБЛИОТЕКИ DLL|DSUIEXT. БИБЛИОТЕКИ DLL|
|GDI32. БИБЛИОТЕКИ DLL|GLU32. БИБЛИОТЕКИ DLL|HLINK. БИБЛИОТЕКИ DLL|ICM32. БИБЛИОТЕКИ DLL|
|IMAGEHLP. БИБЛИОТЕКИ DLL|IMM32. БИБЛИОТЕКИ DLL|IPHLPAPI. БИБЛИОТЕКИ DLL|IPROP. БИБЛИОТЕКИ DLL|
|KERNEL32. БИБЛИОТЕКИ DLL|KSUSER. БИБЛИОТЕКИ DLL|LOADPERF. БИБЛИОТЕКИ DLL|LZ32. БИБЛИОТЕКИ DLL|
|MAPI32. БИБЛИОТЕКИ DLL|MGMTAPI. БИБЛИОТЕКИ DLL|MOBSYNC. БИБЛИОТЕКИ DLL|ПРАВИЛО ПОЛИТИКИ УПРАВЛЕНИЯ. БИБЛИОТЕКИ DLL|
|MPRAPI. БИБЛИОТЕКИ DLL|MQRT. БИБЛИОТЕКИ DLL|MSACM32. БИБЛИОТЕКИ DLL|MSCMS. БИБЛИОТЕКИ DLL|
|MSI. БИБЛИОТЕКИ DLL|MSIMG32. БИБЛИОТЕКИ DLL|MSRATING. БИБЛИОТЕКИ DLL|MSTASK. БИБЛИОТЕКИ DLL|
|MSVFW32. БИБЛИОТЕКИ DLL|MSWSOCK. БИБЛИОТЕКИ DLL|MTXEX. БИБЛИОТЕКИ DLL|NDDEAPI. БИБЛИОТЕКИ DLL|
|NETAPI32. БИБЛИОТЕКИ DLL|NPPTOOLS. БИБЛИОТЕКИ DLL|NTDSAPI. БИБЛИОТЕКИ DLL|NTDSBCLI. БИБЛИОТЕКИ DLL|
|NTMSAPI. БИБЛИОТЕКИ DLL|ODBC32. БИБЛИОТЕКИ DLL|ODBCBCP. БИБЛИОТЕКИ DLL|OLE32. БИБЛИОТЕКИ DLL|
|OLEACC. БИБЛИОТЕКИ DLL|В МОДУЛЕ OLEAUT32. БИБЛИОТЕКИ DLL|OLEDLG. БИБЛИОТЕКИ DLL|OPENGL32. БИБЛИОТЕКИ DLL|
|PDH. БИБЛИОТЕКИ DLL|POWRPROF. БИБЛИОТЕКИ DLL|QOSNAME. БИБЛИОТЕКИ DLL|ЗАПРОС. БИБЛИОТЕКИ DLL|
|RASAPI32. БИБЛИОТЕКИ DLL|RASDLG. БИБЛИОТЕКИ DLL|RASSAPI. БИБЛИОТЕКИ DLL|RESUTILS. БИБЛИОТЕКИ DLL|
|БИБЛИОТЕКИ RICHED20. БИБЛИОТЕКИ DLL|RPCNS4. БИБЛИОТЕКИ DLL|RPCRT4. БИБЛИОТЕКИ DLL|RTM-ВЕРСИИ. БИБЛИОТЕКИ DLL|
|RTUTILS. БИБЛИОТЕКИ DLL|SCARDDLG. БИБЛИОТЕКИ DLL|SECUR32. БИБЛИОТЕКИ DLL|SENSAPI. БИБЛИОТЕКИ DLL|
|SETUPAPI. БИБЛИОТЕКИ DLL|SFC. БИБЛИОТЕКИ DLL|SHELL32. БИБЛИОТЕКИ DLL|SHFOLDER. БИБЛИОТЕКИ DLL|
|SHLWAPI. БИБЛИОТЕКИ DLL|SISBKUP. БИБЛИОТЕКИ DLL|SNMPAPI. БИБЛИОТЕКИ DLL|SRCLIENT. БИБЛИОТЕКИ DLL|
|STI ДЛЯ ПРОЦЕССОРОВ. БИБЛИОТЕКИ DLL|TAPI32. БИБЛИОТЕКИ DLL|ТРАФИК. БИБЛИОТЕКИ DLL|URL-АДРЕС. БИБЛИОТЕКИ DLL|
|URLMON. БИБЛИОТЕКИ DLL|USER32. БИБЛИОТЕКИ DLL|USERENV. БИБЛИОТЕКИ DLL|USP10. БИБЛИОТЕКИ DLL|
|UXTHEME. БИБЛИОТЕКИ DLL|VDMDBG. БИБЛИОТЕКИ DLL|ВЕРСИЯ. БИБЛИОТЕКИ DLL|WINFAX. БИБЛИОТЕКИ DLL|
|WINHTTP. БИБЛИОТЕКИ DLL|WININET. БИБЛИОТЕКИ DLL|WINMM. БИБЛИОТЕКИ DLL|WINSCARD. БИБЛИОТЕКИ DLL|
|WINTRUST. БИБЛИОТЕКИ DLL|WLDAP32. БИБЛИОТЕКИ DLL|WOW32. БИБЛИОТЕКИ DLL|WS2_32.DLL|
|WSNMP32. БИБЛИОТЕКИ DLL|WSOCK32.DLL|WTSAPI32. БИБЛИОТЕКИ DLL|XOLEHLP. БИБЛИОТЕКИ DLL|

> [!NOTE]
>  Сохранение последней ошибки, не поддерживается для неуправляемых функций, которые используются кодом среды CLR в одном модуле.

- Дополнительные сведения см. в разделе [/clr (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр в **Дополнительные параметры** поле.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="example"></a>Пример

В следующем примере определяется собственная библиотека DLL с одну экспортированную функцию, которая изменяет последнюю ошибку.

```
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

В следующем примере используется библиотека DLL, демонстрирующие использование **/CLRSUPPORTLASTERROR**.

```
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

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)