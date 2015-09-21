[Waffle.io](Waffle.io) - канбан-доска для планирования задач и разделения их на группы. Интегрирован с GitHub.
# Разделение задач на группы
| Группа  | Описание                   | Как добавить задачу в группу                 |
| ------- |----------------------------| ---------------------------------------------|
| Backlog | Новые задачи               | Вручную через GitHub/Waffle.io, pull request от conributor'а |
| Ready   | Задачи готовые к выполнению, желательно добавить ссылки на доп. материалы | GitHub (присвоить Label `"ready"`), Waffle.io (перетянуть)|
| In Progress | Задачи, которые сейчас выполняются | GitHub (присвоить Label `"in progress"`),  Waffle.io (перетянуть), запушить ветку с номером таска в названии (например, `dbunit_#100`) |
| Review  | Задачи которые требуют code-review | Waffle.io (перетянуть), с помощью пулл-реквеста (в названии или описании нужно написать номер закрываемой задачи, например, `close #100`) |
| Done    | Закрытые задачи | GitHub(принять пулл-реквест), Waffle.io (перетянуть)|
***
:newspaper: [Статья о похожих срвисах](http://vielmetti.typepad.com/vacuum/2014/11/github-based-kanban-boards-zenhub-waffle-huboard-blossom-et-al.html).

:question: [FAQ](https://github.com/waffleio/waffle.io/wiki/FAQs)

:tv: [Видео 1](https://youtu.be/yEbRaA3rYuA)

:tv: [Видео 2](https://youtu.be/vWR8WkJ735c)