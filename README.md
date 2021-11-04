# NewsPortal for SkillFactory

## Django shell

    from news.models import *
### Задание 1
    user1=User.objects.create_user('user1')
    user2=User.objects.create_user('user2')
### Задание 2
    author1=Author.objects.create(user=user1)
    author2=Author.objects.create(user=user2)
### Задание 3 
    cat1=Category.objects.create(name='Спорт')
    cat2=Category.objects.create(name='Политика')
    cat3=Category.objects.create(name='Образование')
    cat4=Category.objects.create(name='Кулинария')
### Задание 4
    post1=Post.objects.create(author=author1,type=Post.article,title='Статья 1',text='Это текст статьи 1')
    post2=Post.objects.create(author=author2,type=Post.article,title='Статья 2',text='Это текст статьи 2')
    post3=Post.objects.create(author=author2,type=Post.news,title='Новость',text='Это текст новости')
### Задание 5
    post1.category.add(cat1,cat2)
    post2.category.add(cat1,cat3)
    post3.category.add(cat3,cat4,cat2)
### Задание 6
    comm1=Comment.objects.create(post=post1,user=user1,comment='Хорошая статья')
    comm2=Comment.objects.create(post=post1,user=user2,comment='Автор плохо раскрыл тему')
    comm3=Comment.objects.create(post=post2,user=user1,comment='Я ожидал большего')
    comm4=Comment.objects.create(post=post3,user=user2,comment='Шокирующая новость')
### Задание 7
    post1.like()
    post1.like()
    post1.like()
    post2.like()
    post3.like()
    post1.dislike()
    comm1.like()
    comm1.like()
    comm2.like()
    comm2.like()
    comm2.like()
    comm3.like()
    comm4.like()
    comm2.dislike()
### Задание 8
    author1.update_rating()
    author2.update_rating()
### Задание 9
    User.objects.order_by('-author__rating').values('username','author__rating').first()
### Задание 10
    post=Post.objects.order_by('-rating').first()
    post.date
    post.author.user.username
    post.rating
    post.title
    post.preview()
### Задание 11
    post.comment_set.values('date','user__username','rating','comment')