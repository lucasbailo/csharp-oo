## Welcome to a C# project! 👋

### 🎯 Project Objective
The goal of this project is to practice and consolidate the main concepts of Object-Oriented Programming (OOP) using the C# language. Through simple and structured examples, the repository demonstrates in practice the four fundamental pillars of OOP:

- Encapsulation;
- Inheritance;
- Polymorphism;
- Abstraction.

## Built with

- [`.NET 6`](https://dotnet.microsoft.com/download/dotnet/6.0).

## Some code that I'm proud of
```csharp
using ScreenSound.Modelos;
namespace ScreenSound.Menus;

internal class MenuAvaliarAlbum : Menu
{
    public override void Executar(Dictionary<string, Banda> bandasRegistradas)
    {
        base.Executar(bandasRegistradas);
        
        ExibirTituloDaOpcao("Avaliar Album");
        Console.Write("Digite o nome da banda que deseja avaliar: ");
        string nomeDaBanda = Console.ReadLine()!;
        if (bandasRegistradas.ContainsKey(nomeDaBanda))
        {
            Banda banda = bandasRegistradas[nomeDaBanda];
            Console.Write($"Agora digite o título do álbum: ");
            string tituloAlbum = Console.ReadLine()!;
            if (banda.Albuns.Any(a => a.Nome.Equals(tituloAlbum))) 
            { 
                
                Album album = banda.Albuns.First(a => a.Nome.Equals(tituloAlbum));
                
                Console.Write($"Qual a nota que o álbum {tituloAlbum} merece: ");
                Avaliacao nota = Avaliacao.Parse(Console.ReadLine()!);
                album.AdicionarNota(nota);
                Console.WriteLine($"\nA nota {nota.Nota} foi registrada com sucesso para o álbum {tituloAlbum}");
                Thread.Sleep(2000);
                Console.Clear();
            } else
            {
                Console.WriteLine($"\nO álbum {tituloAlbum} não foi encontrado!");
                Console.WriteLine("Digite uma tecla para voltar ao menu principal");
                Console.ReadKey();
                Console.Clear();
            }
        }
        else
        {
            Console.WriteLine($"\nA banda {nomeDaBanda} não foi encontrada!");
            Console.WriteLine("Digite uma tecla para voltar ao menu principal");
            Console.ReadKey();
            Console.Clear();
        } 
    }
}
```

## Author

- Website - [My GitHub](https://github.com/lucasbailo)
- Frontend Mentor - [@lucasbailo](https://www.frontendmentor.io/profile/lucasbailo)
- Instagram - [@lucassbailo](https://www.instagram.com/lucassbailo/)
- LinkedIn - [Lucas Bailo](https://www.linkedin.com/in/lcsbailo)
