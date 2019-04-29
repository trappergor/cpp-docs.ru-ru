---
title: _get_purecall_handler, _set_purecall_handler
ms.date: 11/04/2016
apiname:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
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
apitype: DLLExport
f1_keywords:
- _set_purecall_handler
- _set_purecall_handler_m
- set_purecall_handler_m
- set_purecall_handler
- stdlib/_set_purecall_handler
- stdlib/_get_purecall_handler
- _get_purecall_handler
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
ms.openlocfilehash: 0009b4bc1c7bf70bd84b9a82ecdc8643789e8164
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287404"
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler, _set_purecall_handler

Получает или задает обработчик ошибок для вызова чистой виртуальной функции.

## <a name="syntax"></a>Синтаксис

```cpp
typedef void (__cdecl* _purecall_handler)(void);
_purecall_handler __cdecl _get_purecall_handler(void);
_purecall_handler __cdecl _set_purecall_handler(
   _purecall_handler function
);
```

### <a name="parameters"></a>Параметры

*function*<br/>
Эту функцию необходимо вызывать при вызове чистой виртуальной функции. Объект **_purecall_handler** функция должна иметь возвращаемый тип void.

## <a name="return-value"></a>Возвращаемое значение

Предыдущий **_purecall_handler**. Возвращает **nullptr** Если там не было предыдущего обработчика.

## <a name="remarks"></a>Примечания

**_Get_purecall_handler** и **_set_purecall_handler** функции, характерные для Майкрософт и применяются только к C++ кода.

Вызов чистой виртуальной функции является ошибкой, так как она не имеет реализации. По умолчанию компилятор создает код для вызова функции обработчика ошибок при вызове чистой виртуальной функции, который завершает программу. Можно установить собственный обработчик ошибок для вызовов чистых виртуальных функций, который будет перехватывать их в целях отладки или ведения отчетности. Чтобы использовать собственный обработчик ошибок, создайте функцию, которая имеет **_purecall_handler** подпись, затем с помощью **_set_purecall_handler** для упрощения текущего обработчика.

Поскольку имеется только один **_purecall_handler** для каждого процесса, при вызове **_set_purecall_handler** он немедленно применяются ко всем потокам. Последний вызывающий элемент в любом потоке задает обработчик.

Чтобы восстановить поведение по умолчанию, вызовите **_set_purecall_handler** с помощью **nullptr** аргумент.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_get_purecall_handler**, **_set_purecall_handler**|\<cstdlib> или \<stdlib.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```cpp
// _set_purecall_handler.cpp
// compile with: /W1
#include <tchar.h>
#include <stdio.h>
#include <stdlib.h>

class CDerived;
class CBase
{
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function(void) = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase
{
public:
   CDerived() : CBase(this) {};   // C4355
   virtual void function(void) {};
};

CBase::~CBase()
{
   m_pDerived -> function();
}

void myPurecallHandler(void)
{
   printf("In _purecall_handler.");
   exit(0);
}

int _tmain(int argc, _TCHAR* argv[])
{
   _set_purecall_handler(myPurecallHandler);
   CDerived myDerived;
}
```

```Output
In _purecall_handler.
```

## <a name="see-also"></a>См. также

[Обработка ошибок](../../c-runtime-library/error-handling-crt.md)<br/>
[_purecall](purecall.md)<br/>
