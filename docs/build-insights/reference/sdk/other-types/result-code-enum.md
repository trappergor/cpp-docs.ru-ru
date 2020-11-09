---
title: Перечисление RESULT_CODE
description: Справочник по перечислению RESULT_CODE пакета SDK для Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- RESULT_CODE
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3d9d18d535d15d04a2e449bdbbf693364276a518
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922410"
---
# <a name="result_code-enum"></a>Перечисление RESULT_CODE

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Перечисление `RESULT_CODE` описывает условия успешного выполнения и сбоя.

## <a name="members"></a>Члены

| Имя | Значение | Описание |
|--|--|--|
| `RESULT_CODE_SUCCESS` | 0 (0x00000000) | Операция выполнена успешно. |
| `RESULT_CODE_FAILURE_ANALYSIS_ERROR` | 1 (0x00000001) | Одна из функций обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) вернула значение `CALLBACK_CODE_ANALYSIS_FAILURE`. Это значение является членом перечисления [CALLBACK_CODE](callback-code-enum.md). |
| `RESULT_CODE_FAILURE_CANCELLED` | 2 (0x00000002) | Одна из функций обратного вызова в [ANALYSIS_DESCRIPTOR](analysis-descriptor-struct.md) или [RELOG_DESCRIPTOR](relog-descriptor-struct.md) вернула значение `CALLBACK_CODE_ANALYSIS_CANCEL`. Это значение является членом перечисления [CALLBACK_CODE](callback-code-enum.md). |
| `RESULT_CODE_FAILURE_INVALID_INPUT_LOG_FILE` | 3 (0x00000003) | Указана недопустимая входная трассировка событий для Windows (ETW). |
| `RESULT_CODE_FAILURE_INVALID_OUTPUT_LOG_FILE` | 4 (0x00000004) | Указана недопустимая выходная трассировка событий Windows. |
| `RESULT_CODE_FAILURE_MISSING_ANALYSIS_CALLBACK` | 5 (0x00000005) | Неверная инициализация структуры [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md). |
| `RESULT_CODE_FAILURE_MISSING_RELOG_CALLBACK` | 6 (0x00000006) | Неверная инициализация структуры [RELOG_CALLBACKS](relog-callbacks-struct.md). |
| `RESULT_CODE_FAILURE_OPEN_INPUT_TRACE` | 7 (0x00000007) | Не удалось открыть входную трассировку событий Windows. |
| `RESULT_CODE_FAILURE_PROCESS_TRACE` | 8 (0x00000008) | При обработке входной трассировки событий Windows произошла ошибка. |
| `RESULT_CODE_FAILURE_START_RELOGGER` | 9 (0x00000009) | При попытке запустить сеанс повторного входа произошла ошибка. |
| `RESULT_CODE_FAILURE_DROPPED_EVENTS` | 10 (0x0000000A) | Во входной трассировке событий Windows отсутствуют важные события. |
| `RESULT_CODE_FAILURE_UNSUPPORTED_OS` | 11 (0x0000000B) | Вы используете Аналитику сборки C++ для неподдерживаемой версии Windows. |
| `RESULT_CODE_FAILURE_INVALID_TRACING_SESSION_NAME` | 12 (0x0000000C) | Указанное имя сеанса недопустимо. |
| `RESULT_CODE_FAILURE_INSUFFICIENT_PRIVILEGES` | 13 (0x0000000D) | Для выполнения операции требуются разрешения администратора. |
| `RESULT_CODE_FAILURE_GENERATE_GUID` | 14 (0x0000000E) | Во время создания GUID произошла ошибка. |
| `RESULT_CODE_FAILURE_OBTAINING_TEMP_DIRECTORY` | 15 (0x0000000F) | При попытке определить путь к временному каталогу произошла ошибка. |
| `RESULT_CODE_FAILURE_CREATE_TEMPORARY_DIRECTORY` | 16 (0x00000010) | При попытке создать временный каталог для запущенного сеанса трассировки произошла ошибка. |
| `RESULT_CODE_FAILURE_START_SYSTEM_TRACE` | 17 (0x00000011) | При попытке запустить трассировку системы произошла ошибка. |
| `RESULT_CODE_FAILURE_START_MSVC_TRACE` | 18 (0x00000012) | При попытке запустить трассировку MSVC произошла ошибка. |
| `RESULT_CODE_FAILURE_STOP_MSVC_TRACE` | 19 (0x00000013) | При попытке прекратить трассировку MSVC произошла ошибка. |
| `RESULT_CODE_FAILURE_STOP_SYSTEM_TRACE` | 20 (0x00000014) | При попытке запустить трассировку системы произошла ошибка. |
| `RESULT_CODE_FAILURE_SESSION_DIRECTORY_RESOLUTION` | 21 (0x00000015) | Трассировка остановлена, однако не удается найти временный каталог сеанса трассировки. |
| `RESULT_CODE_FAILURE_MSVC_TRACE_FILE_NOT_FOUND` | 22 (0x00000016) | Не удается найти файл трассировки для остановленной трассировки MSVC. |
| `RESULT_CODE_FAILURE_MERGE_TRACES` | 23 (0x00000017) | При слиянии трассировок с помощью Средства трассировки на уровне ядра произошла ошибка. |
| `RESULT_CODE_FAILURE_UNKNOWN_ERROR` | 24 (0x00000018) | Произошла неизвестная ошибка. |

::: moniker-end
