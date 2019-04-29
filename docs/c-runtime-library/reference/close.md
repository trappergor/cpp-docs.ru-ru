---
title: _close
ms.date: 11/04/2016
apiname:
- _close
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _close
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
ms.openlocfilehash: faea008903136e8abdc39297672b31800ada796d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340018"
---
# <a name="close"></a>_close

Закрывает файл.

## <a name="syntax"></a>Синтаксис

```C
int _close(
   int fd
);
```

### <a name="parameters"></a>Параметры

*fd*<br/>
Дескриптор файла, ссылающийся на открытый файл.

## <a name="return-value"></a>Возвращаемое значение

**_Закрыть** возвращает 0, если файл был успешно закрыт. Возвращаемое значение-1 указывает на ошибку.

## <a name="remarks"></a>Примечания

**_Close** функция закрывает файл, связанный с *fd*.

Дескриптор файла и соответствующий обработчик файлов операционной системы закрываются. Таким образом, нет необходимости вызывать **CloseHandle** Если файл был открыт с помощью функции Win32 **CreateFile** и преобразован в дескриптор файлов с помощью **_open_osfhandle**.

Эта функция проверяет свои параметры. Если *fd* является недопустимым дескриптором, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функции возвращают -1 и **errno** присваивается **значение EBADF**.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_close**|\<io.h>|\<errno.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

См. пример для [_open](open-wopen.md).

## <a name="see-also"></a>См. также

[Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)<br/>
[_chsize](chsize.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_unlink, _wunlink](unlink-wunlink.md)<br/>
