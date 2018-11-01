---
title: Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows
ms.date: 12/30/2016
ms.assetid: cbfc957d-6c60-48f4-97e3-1ed8526743b4
ms.openlocfilehash: 2de3edb11d65236f14c4c8fdf52fe6c855399dba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527690"
---
# <a name="crt-functions-not-supported-in-universal-windows-platform-apps"></a>Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows

Многие функции среды выполнения C (CRT) недоступны при построении приложений универсальной платформы Windows. В некоторых случаях доступны обходные решения, — например, можно использовать среду выполнения Windows или API-интерфейсов Win32. Однако в других случаях функции CRT запрещены, поскольку соответствующие им функции или вспомогательные API не могут применяться к приложениям UWP. Чтобы найти альтернативный метод, который поддерживается для среды выполнения Windows, см. в разделе [альтернативы интерфейсов API Windows в приложениях UWP](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

В следующей таблице перечислены функции CRT, которые недоступны при построении приложений UWP, и приведены применимые решения.

## <a name="unsupported-crt-functions"></a>Неподдерживаемые функции CRT

||||
|-|-|-|
|_beep _sleep _seterrormode|Эти функции устарели в предыдущих версиях CRT. Кроме того, соответствующие API Win32 недоступны для приложений UWP.|Обходное решение отсутствует.|
|chdir _chdrive getcwd|Эти функции являются устаревшими или не являются потокобезопасными.|Используйте _chdir, _getcwd и связанные функции.|
|_cgets _cgets_s _cgetws _cgetws_s _cprintf _cprintf_l _cprintf_p _cprintf_p_l _cprintf_s _cprintf_s_l _cputs _cputws _cscanf _cscanf_l _cscanf_s _cscanf_s_l _cwait _cwprintf _cwprintf_l _cwprintf_p _cwprintf_p_l _cwprintf_s _cwprintf_s_l _cwscanf _cwscanf_l _cwscanf_s _cwscanf_s_l _vcprintf _vcprintf_l _vcprintf_p _vcprintf_p_l _vcprintf_s _vcprintf_s_l _vcwprintf _vcwprintf_l _vcwprintf_p _vcwprintf_p_l _vcwprintf_s _vcwprintf_s_l _getch _getch_nolock _getche _getche_nolock _getwch _getwch_nolock _getwche _getwche_nolock _putch _putch_nolock _putwch _putwch_nolock _ungetch _ungetch_nolock _ungetwch _ungetwch_nolock _kbhit kbhit putch cgets cprintf cputs cscanf cwait getch getche ungetch|Эти функции используются для чтения напрямую с консоли и записи на консоль. Приложения UWP имеют только графический пользовательский интерфейс и не поддерживают консоль.|Обходное решение отсутствует.|
|getpid|Эта функция устарела.|Используйте _getpid или API Win32 `GetCurrentProcessId()`.|
|_getdiskfree|Недоступно.|Используйте API Win32 `GetDiskFreeSpaceExW()`.|
|_getdrive _getdrives|Соответствующий API недоступен для приложений UWP.|Обходное решение отсутствует.|
|_inp _inpd _inpw _outp _outpd _outpw inp inpd inpw outp outpd outpw|Ввод-вывод через порты не поддерживается в приложениях UWP.|Обходное решение отсутствует.|
|_ismbcalnum _ismbcalnum_l _ismbcalpha _ismbcalpha_l _ismbcdigit _ismbcdigit_l _ismbcgraph _ismbcgraph_l _ismbchira _ismbchira_l _ismbckata _ismbckata_l _ismbcl0 _ismbcl0_l _ismbcl1 _ismbcl1_l _ismbcl2 _ismbcl2_l _ismbclegal _ismbclegal_l _ismbclower _ismbclower_l _ismbcprint _ismbcprint_l _ismbcpunct _ismbcpunct_l _ismbcspace _ismbcspace_l _ismbcsymbol _ismbcsymbol_l _ismbcupper _ismbcupper_l _mbbtombc _mbbtombc_l _mbbtype _mbbtype_l _mbccpy _mbccpy_l _mbccpy_s _mbccpy_s_l _mbcjistojms _mbcjistojms_l _mbcjmstojis _mbcjmstojis_l _mbclen _mbclen_l _mbctohira _mbctohira_l _mbctokata _mbctokata_l _mbctolower _mbctolower_l _mbctombb _mbctombb_l _mbctoupper _mbctoupper_l _mbsbtype _mbsbtype_l _mbscat _mbscat_l _mbscat_s _mbscat_s_l _mbschr _mbschr_l _mbscmp _mbscmp_l _mbscoll _mbscoll_l _mbscpy _mbscpy_l _mbscpy_s _mbscpy_s_l _mbscspn _mbscspn_l _mbsdec _mbsdec_l _mbsicmp _mbsicmp_l _mbsicoll _mbsicoll_l _mbsinc _mbsinc_l _mbslen _mbslen_l _mbslwr _mbslwr_l _mbslwr_s _mbslwr_s_l _mbsnbcat _mbsnbcat_l _mbsnbcat_s _mbsnbcat_s_l _mbsnbcmp _mbsnbcmp_l _mbsnbcnt _mbsnbcnt_l _mbsnbcoll _mbsnbcoll_l _mbsnbcpy _mbsnbcpy_l _mbsnbcpy_s _mbsnbcpy_s_l _mbsnbicmp _mbsnbicmp_l _mbsnbicoll _mbsnbicoll_l _mbsnbset _mbsnbset_l _mbsnbset_s _mbsnbset_s_l _mbsncat _mbsncat_l _mbsncat_s _mbsncat_s_l _mbsnccnt _mbsnccnt_l _mbsncmp _mbsncmp_l _mbsncoll _mbsncoll_l _mbsncpy _mbsncpy_l _mbsncpy_s _mbsncpy_s_l _mbsnextc _mbsnextc_l _mbsnicmp _mbsnicmp_l _mbsnicoll _mbsnicoll_l _mbsninc _mbsninc_l _mbsnlen _mbsnlen_l _mbsnset _mbsnset_l _mbsnset_s _mbsnset_s_l _mbspbrk _mbspbrk_l _mbsrchr _mbsrchr_l _mbsrev _mbsrev_l _mbsset _mbsset_l _mbsset_s _mbsset_s_l _mbsspn _mbsspn_l _mbsspnp _mbsspnp_l _mbsstr _mbsstr_l _mbstok _mbstok_l _mbstok_s _mbstok_s_l _mbsupr _mbsupr_l _mbsupr_s _mbsupr_s_l is_wctype|Многобайтовые строки не поддерживаются в приложениях UWP.|Используйте вместо них строки Юникода.|
|_pclose _pipe _popen _wpopen|Именованные каналы недоступны для приложений UWP.|Обходное решение отсутствует.|
|_resetstkoflw|Вспомогательные API Win32 недоступны для приложений UWP.|Обходное решение отсутствует.|
|_getsystime _setsystime|Эти API устарели в предыдущих версиях CRT. Кроме того, пользователь не может задать системное время в приложении UWP из-за отсутствия необходимых разрешений.|Для получения системного времени используйте API Win32 `GetSystemTime`. Системное время нельзя устанавливать.|
|_environ _putenv _putenv_s _searchenv _searchenv_s _dupenv_s _wputenv _wputenv_s _wsearchenv getenv getenv_s putenv _wdupenv_s _wenviron _wgetenv _wgetenv_s _wsearchenv_s tzset|Переменные среды недоступны для приложений UWP.|Обходное решение отсутствует. Чтобы установить часовой пояс, используйте _tzset.|
|_loaddll _getdllprocaddr _unloaddll|Эти функции устарели в предыдущих версиях CRT. Кроме того, пользователь не может загружать библиотеки DLL, отличные от DLL из пакета самого приложения.|Для загрузки и использования упакованных DLL следует применять API Win32 `LoadPackagedLibrary`, `GetProcAddress`и `FreeLibrary` .|
|_wexecl _wexecle _wexeclp _wexeclpe _wexecv _wexecve _wexecvp _wexecvpe _execl _execle _execlp _execlpe _execv _execve _execvp _execvpe _spawnl _spawnle _spawnlp _spawnlpe _spawnv _spawnve _spawnvp _spawnvpe _wspawnl _wspawnle _wspawnlp _wspawnlpe _wspawnv _wspawnve _wspawnvp _wspawnvpe _wsystem execl execle execlp execlpe execv execve execvp execvpe spawnl spawnle spawnlp spawnlpe spawnv spawnve spawnvp spawnvpe system|Эта функциональность недоступна для приложений UWP. Приложение UWP не может вызывать другое приложение UWP или классическое приложение.|Обходное решение отсутствует.|
|_heapwalk _heapadd _heapchk _heapset _heapused|Эти функции обычно используются для работы с кучей. Однако соответствующие API Win32 не поддерживаются в приложениях UWP. И приложения больше не могут создавать и использовать закрытые кучи.|Обходное решение отсутствует. Но функция `_heapwalk` доступна в DEBUG CRT для целей отладки. Их нельзя использовать в приложениях, которые отправляются в Microsoft Store.|

Следующие функции доступны в CRT для приложений универсальной платформы Windows, но должен использоваться только в том случае, если нельзя использовать соответствующий Win32 или API среды выполнения Windows — например, при переносе больших объемов кода

|||
|-|-|
|Однобайтовые строковые функции, например `strcat`, `strcpy`, `strlwr`и так далее.|Сделайте свои приложения UWP только Юникод, так как все API-интерфейсов Win32 и API среды выполнения Windows, представляемые используют только наборы символов Юникода.  Однобайтовые функции были сохранены для переноса больших объемов кода; в остальных случаях их следует избегать и по возможности использовать соответствующие функции для работы с расширенными символами.|
|Функции ввода-вывода потоков и ввода-вывода файлов нижнего уровня, например `fopen`, `open`и так далее.|Эти функции являются синхронными, т. е. их не рекомендуется использовать в приложениях UWP. В приложениях UWP для открытия, чтения и записи файлов используйте асинхронные API, чтобы избежать блокировки потока пользовательского интерфейса. Примеры таких API можно найти в классе `Windows::Storage::FileIO` .|

## <a name="windows-8x-store-apps-and-windows-phone-8x-apps"></a>Приложения для Магазина Windows 8.x и приложения Windows Phone 8.x

Помимо упомянутых ранее API, следующие API недоступны в приложениях Магазина Windows 8.x и приложениях Windows Phone 8.x.

||||
|-|-|-|
|_beginthread _beginthreadex _endthread _endthreadex|Потоковые API Win32 недоступны в приложениях для Магазина Windows 8.x.|Вместо них следует использовать `Windows Runtime Windows::System::Threading::ThreadPool` или `concurrency::task` .|
|_chdir _wchdir _getcwd _getdcwd _wgetcwd _wgetdcwd|Понятие рабочего каталога не применяется к приложениям для Магазина Windows 8.x.|Используйте полные пути.|
|_getpid|Эти функции устарели в предыдущих версиях CRT.|Используйте API Win32 `GetCurrentProcessId()`.|
|_isleadbyte_l _ismbbalnum, _ismbbalnum_l, _ismbbalpha, _ismbbalpha _ismbbalpha_l _ismbbgraph _ismbbgraph_l _ismbbkalnum _ismbbkalnum_l _ismbbkana _ismbbkana_l _ismbbkprint _ismbbkprint_l _ismbbkpunct _ismbbkpunct_l _ismbblead _ismbblead_l _ismbbprint _ismbbprint_l _ismbbpunct _ismbbpunct_l _ismbbtrail _ismbbtrail_l _ismbslead _ismbslead_l _ismbstrail _ismbstrail_l _mbsdup isleadbyte|Многобайтовые строки не поддерживаются в приложениях Магазина Windows 8.x.|Используйте вместо них строки Юникода.|
|_tzset|Переменные среды недоступны для приложений Магазина Windows 8.x.|Обходное решение отсутствует.|
|_get_heap_handle, _heapmin|Соответствующие API Win32 не поддерживаются в приложениях Магазина Windows 8.x. И приложения больше не могут создавать закрытые кучи.|Обходное решение отсутствует. Но функция `_get_heap_handle` доступна в DEBUG CRT для целей отладки.|