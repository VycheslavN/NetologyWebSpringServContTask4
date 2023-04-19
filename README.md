# Домашнее задание к занятию «2.3. Spring Web MVC»
В качестве решения пришлите ссылки на ваши GitHub-проекты в личном кабинете студента на сайте netology.ru.

### Важная информация

Перед стартом работы изучите, пожалуйста, ссылки на главной странице репозитория с домашними заданиями.
Если у вас что-то не получилось, тогда оформляйте Issue по установленным правилам.
## Как сдавать задачи
Создайте на вашем компьютере Maven-проект.
Инициализируйте в нём пустой Git-репозиторий.
Добавьте в него готовый файл .gitignore.
Добавьте в этот же каталог остальные необходимые файлы.
Сделайте необходимые коммиты.
Создайте публичный репозиторий на GitHub и свяжите свой локальный репозиторий с удалённым.
Сделайте пуш и удостоверьтесь, что ваш код появился на GitHub.
Ссылку на ваш проект отправьте в личном кабинете на сайте netology.ru.
## Migration
### Легенда
Первая задача простая: нужно смигрировать ваше приложение на сервлетах, написанное в предыдущих домашних заданиях, на Spring Web MVC с Embed Tomcat.

### Задача
Создайте новый проект на базе Spring MVC и Embed Tomcat и перенесите реализованную в предыдущих домашних заданиях функциональность.

Ваш контроллер должен выглядеть именно так, как в лекции:

@RestController
@RequestMapping("/api/posts")
public class PostController {
private final PostService service;

public PostController(PostService service) {
this.service = service;
}

@GetMapping
public List<Post> all() {
return service.all();
}

@GetMapping("/{id}")
public Post getById(@PathVariable long id) {
return service.getById(id);
}

@PostMapping
public Post save(@RequestBody Post post) {
return service.save(post);
}

@DeleteMapping("/{id}")
public void removeById(long id) {
service.removeById(id);
}
}
Обратите внимание, что вся функциональность (CRUD), реализованная до этого, должна по-прежнему работать.

### Результат
В качестве результата пришлите ссылку на ваш GitHub-проект в личном кабинете студента на сайте netology.ru.
