---
title: Перечисление RESULT_CODE
description: В C++ пакете SDK для аналитики сборки RESULT_CODE ссылка перечисления.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RESULT_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ee563d148b3456b288bc418255ec46f8cbade7ec
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333950"
---
# <a name="result_code-enum"></a>Перечисление RESULT_CODE

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Перечисление `RESULT_CODE` описывает условия успеха и сбоя.

## <a name="members"></a>Члены

| Имя | Значение | Description |
|--|--|--|
| `RESULT_CODE_SUCCESS` | 0 (0x00000000) | Операция прошла успешно. |
| `RESULT_CODE_FAILURE_ANALYSIS_ERROR` | 1 (0x00000001) | Одна из функций обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) вернула значение `CALLBACK_CODE_ANALYSIS_FAILURE`. Это значение является членом перечисления [CALLBACK_CODE](callback-code-enum.md) . |
| `RESULT_CODE_FAILURE_CANCELLED` | 2 (0x00000002) | Одна из функций обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) вернула значение `CALLBACK_CODE_ANALYSIS_CANCEL`. Это значение является членом перечисления [CALLBACK_CODE](callback-code-enum.md) . |
| `RESULT_CODE_FAILURE_INVALID_INPUT_LOG_FILE` | 3 (0x00000003) | Указана недопустимая трассировка входных событий для Windows (ETW). |
| `RESULT_CODE_FAILURE_INVALID_OUTPUT_LOG_FILE` | 4 (0x00000004) | Указана недопустимая выходная трассировка ETW. |
| `RESULT_CODE_FAILURE_MISSING_ANALYSIS_CALLBACK` | 5 (0x00000005) | Структура [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) не была правильно инициализирована. |
| `RESULT_CODE_FAILURE_MISSING_RELOG_CALLBACK` | 6 (0x00000006) | Структура [RELOG_CALLBACKS](relog-callbacks-struct.md) не была правильно инициализирована. |
| `RESULT_CODE_FAILURE_OPEN_INPUT_TRACE` | 7 (0x00000007) | Не удалось открыть входную трассировку ETW. |
| `RESULT_CODE_FAILURE_PROCESS_TRACE` | 8 (0x00000008) | Произошла ошибка при обработке входной трассировки ETW. |
| `RESULT_CODE_FAILURE_START_RELOGGER` | 9 (0x00000009) | Произошла ошибка при попытке запустить сеанс повторного ведения журнала. |
| `RESULT_CODE_FAILURE_DROPPED_EVENTS` | 10 (0x0000000A) | В входной трассировке ETW отсутствуют важные события. |
| `RESULT_CODE_FAILURE_UNSUPPORTED_OS` | 11 (0x0000000B) | Вы используете C++ аналитику сборки для неподдерживаемой версии Windows. |
| `RESULT_CODE_FAILURE_INVALID_TRACING_SESSION_NAME` | 12 (0x0000000C) | Указано недопустимое имя сеанса. |
| `RESULT_CODE_FAILURE_INSUFFICIENT_PRIVILEGES` | 13 (0x0000000D) | Для этой операции требуются права администратора. |
| `RESULT_CODE_FAILURE_GENERATE_GUID` | 14 (0x0000000E) | Произошла ошибка при формировании идентификатора GUID. |
| `RESULT_CODE_FAILURE_OBTAINING_TEMP_DIRECTORY` | 15 (0x0000000F) | Произошла ошибка при попытке определить путь к временному каталогу. |
| `RESULT_CODE_FAILURE_CREATE_TEMPORARY_DIRECTORY` | 16 (0x00000010) | Произошла ошибка при попытке создать временный каталог для запущенного сеанса трассировки. |
| `RESULT_CODE_FAILURE_START_SYSTEM_TRACE` | 17 (0x00000011) | Произошла ошибка при попытке запустить трассировку системы. |
| `RESULT_CODE_FAILURE_START_MSVC_TRACE` | 18 (0x00000012) | Произошла ошибка при попытке запустить трассировку КОМПИЛЯТОРОМ MSVC. |
| `RESULT_CODE_FAILURE_STOP_MSVC_TRACE` | 19 (0x00000013) | Произошла ошибка при попытке прекращения трассировки КОМПИЛЯТОРОМ MSVC. |
| `RESULT_CODE_FAILURE_STOP_SYSTEM_TRACE` | 20 (0x00000014) | Произошла ошибка при попытке запустить трассировку системы. |
| `RESULT_CODE_FAILURE_SESSION_DIRECTORY_RESOLUTION` | 21 (0x00000015) | Трассировка была остановлена, но не удается найти временный каталог сеанса трассировки. |
| `RESULT_CODE_FAILURE_MSVC_TRACE_FILE_NOT_FOUND` | 22 (0x00000016) | Не удается найти файл трассировки для останавливаемой трассировки КОМПИЛЯТОРОМ MSVC. |
| `RESULT_CODE_FAILURE_MERGE_TRACES` | 23 (0x00000017) | Произошла ошибка при слиянии трассировок с помощью элемента управления трассировки ядра. |
| `RESULT_CODE_FAILURE_UNKNOWN_ERROR` | 24 (0x00000018) | Произошла неизвестная ошибка. |

::: moniker-end
