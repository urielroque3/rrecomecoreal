# rrecomecoreal
import React, { useState, useEffect } from 'react';
import { Button } from "/components/ui/button";
import { Card, CardContent, CardHeader, CardTitle } from "/components/ui/card";
const LandingPageEmagrecimento = () => {
  const [timeLeft, setTimeLeft] = useState({
    hours: 23,
    minutes: 45,
    seconds: 30
  });
  useEffect(() => {
    const timer = setInterval(() => {
      setTimeLeft(prev => {
        if (prev.seconds > 0) {
          return { ...prev, seconds: prev.seconds - 1 };
        } else if (prev.minutes > 0) {
          return { ...prev, minutes: prev.minutes - 1, seconds: 59 };
        } else if (prev.hours > 0) {
          return { hours: prev.hours - 1, minutes: 59, seconds: 59 };
        }
        return prev;
      });
    }, 1000);
    return () => clearInterval(timer);
  }, []);
  const scrollToSection = (id: string) => {
    const element = document.getElementById(id);
    element?.scrollIntoView({ behavior: 'smooth' });
  };
  return (
    <div className="min-h-screen bg-background">
      {/* Header */}
      <header className="bg-primary text-primary-foreground py-4 sticky top-0 z-50">
      <div className="max-w-6xl mx-auto px-4 flex justify-between items-center">
          <h1 className="text-2xl font-bold">Recomeço Real</h1>
          <Button 
            variant="secondary" 
            onClick={() => scrollToSection('comprar')}
            className="bg-accent text-accent-foreground hover:bg-accent/90"
          >
            Quero Emagrecer Agora
          </Button>
        </div>
      </header>
      {/* Hero Section */}
      <section className="bg-gradient-to-br from-primary/10 to-secondary/10 py-20">
        <div className="max-w-6xl mx-auto px-4 text-center">
          <div className="mb-8">
            <img 
              src="https://placeholder-image-service.onrender.com/image/400x300?prompt=Before and after transformation showing a confident woman celebrating weight loss success with measuring tape and healthy foods&id=c5743415-f204-4685-bf53-cadc5daad77d&customer_id=cus_T37mvv9upb5WPT"
              alt="Transformação de emagrecimento mostrando mulher confiante celebrando perda de peso com fita métrica e alimentos saudáveis"
              className="mx-auto rounded-lg shadow-lg mb-8 w-full max-w-md"
            />
          </div>
          
          <h2 className="text-4xl md:text-6xl font-bold text-foreground mb-6">
            <span className="text-primary">Recomeço Real:</span><br />
            Emagrecimento Sem Volta
          </h2>
          
          <p className="text-xl text-muted-foreground mb-8 max-w-3xl mx-auto">
            O método completo que vai transformar sua relação com a comida e seu corpo 
            para <span className="font-semibold text-primary">sempre</span>. 
            Pare de fazer dietas que não funcionam!
          </p>
          <Button 
            size="lg" 
            className="text-xl px-12 py-6 bg-primary hover:bg-primary/90"
            onClick={() => scrollToSection('comprar')}
          >
            Começar Minha Transformação - R$ 67,90
          </Button>
        </div>
      </section>
      {/* Problemas que resolve */}
      <section className="py-20 bg-muted/50">
        <div className="max-w-6xl mx-auto px-4">
          <h3 className="text-3xl font-bold text-center mb-12">
            Você está cansada de...
          </h3>
          
          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            <Card className="bg-background border-destructive/20">
              <CardHeader>
                <CardTitle className="text-destructive">❌ Efeito Sanfona</CardTitle>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  Perder peso e recuperar tudo (e mais um pouco) em poucos meses
                </p>
              </CardContent>
            </Card>
            <Card className="bg-background border-destructive/20">
              <CardHeader>
                <CardTitle className="text-destructive">❌ Dietas Restritivas</CardTitle>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  Passar fome e se privar dos alimentos que gosta sem resultados duradouros
                </p>
              </CardContent>
            </Card>
                <p className="text-muted-foreground">
                  Comer por emoção e se sentir culpada depois de cada refeição
                </p>
              </CardContent>
            </Card>
            <Card className="bg-background border-destructive/20">
              <CardHeader>
                <CardTitle className="text-destructive">❌ Falta de Energia</CardTitle>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  Se sentir cansada e sem disposição para as atividades do dia a dia
                </p>
              </CardContent>
            </Card>
            <Card className="bg-background border-destructive/20">
              <CardHeader>
                <CardTitle className="text-destructive">❌ Métodos Confusos</CardTitle>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  Não saber por onde começar com tantas informações contraditórias
                </p>
              </CardContent>
            </Card>
          </div>
        </div>
      </section>
{/* Solução */}
      <section className="py-20">
        <div className="max-w-6xl mx-auto px-4 text-center">
          <h3 className="text-3xl font-bold mb-8">
            Agora imagine como seria...
          </h3>
          
          <div className="grid md:grid-cols-2 gap-12 items-center">
            <div>
              <img 
                src="https://placeholder-image-service.onrender.com/image/500x400?prompt=Happy confident woman in workout clothes preparing healthy colorful meal in modern kitchen with fruits and vegetables&id=c5743415-f204-4685-bf53-cadc5daad77d&customer_id=cus_T37mvv9upb5WPT"
                alt="Mulher feliz e confiante em roupas de exercício preparando refeição saudável e colorida em cozinha moderna com frutas e vegetais"
                className="rounded-lg shadow-lg w-full"
              />
            </div>
            
            <div className="text-left">
              <ul className="space-y-4 text-lg">
                <li className="flex items-start gap-3">
                  <span className="text-primary font-bold">✅</span>
                  <span>Acordar todos os dias se sentindo <strong>leve e energizada</strong></span>
                </li>
                <li className="flex items-start gap-3">
                  <span className="text-primary font-bold">✅</span>
                  <span>Usar as roupas que sempre sonhou com <strong>total confiança</strong></span>
                </li>
                 <li className="flex items-start gap-3">
                  <span className="text-primary font-bold">✅</span>
                  <span>Comer sem culpa, sabendo que está <strong>nutrindo seu corpo</strong></span>
                </li>
                <li className="flex items-start gap-3">
                  <span className="text-primary font-bold">✅</span>
                  <span>Ter uma <strong>relação saudável</strong> com a comida para sempre</span>
                </li>
                <li className="flex items-start gap-3">
                  <span className="text-primary font-bold">✅</span>
                  <span>Manter seu peso ideal <strong>sem esforço</strong> ou restrições extremas</span>
                </li>
              </ul>
              
              <div className="mt-8">
                <Button 
                  size="lg" 
                  className="bg-primary hover:bg-primary/90"
                  onClick={() => scrollToSection('comprar')}
                >
                  Quero Essa Transformação
                </Button>
              </div>
            </div>
          </div>
        </div>
      </section>

          </h3>
          
          <div className="grid lg:grid-cols-2 gap-8">
            <Card className="bg-background">
              <CardHeader>
                <img 
                  src="https://placeholder-image-service.onrender.com/image/400x200?prompt=Digital course module icon showing brain with gears representing mindset transformation and psychology&id=c5743415-f204-4685-bf53-cadc5daad77d&customer_id=cus_T37mvv9upb5WPT"
                  alt="Ícone de módulo de curso digital mostrando cérebro com engrenagens representando transformação mental e psicologia"
                  className="w-full rounded-lg mb-4"
                />
                <CardTitle className="text-primary">Módulo 1: Mindset de Emagrecimento</CardTitle>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-muted-foreground">
                  <li>• Como reprogramar sua mente para o sucesso</li>
                  <li>• Identificar e quebrar padrões sabotadores</li>
                  <li>• Desenvolver uma mentalidade vencedora</li>
                  <li>• Técnicas de motivação duradoura</li>
                </ul>
              </CardContent>
            </Card>
            <Card className="bg-background">
              <CardHeader>
                <img 
                  src="https://placeholder-image-service.onrender.com/image/400x200?prompt=Nutritious balanced meal with colorful vegetables proteins and whole grains arranged beautifully on plate&id=c5743415-f204-4685-bf53-cadc5daad77d&customer_id=cus_T37mvv9upb5WPT"
                  alt="Refeição equilibrada e nutritiva com vegetais coloridos proteínas e grãos integrais dispostos lindamente no prato"
                  className="w-full rounded-lg mb-4"
                />
                <CardTitle className="text-primary">Módulo 2: Alimentação Inteligente</CardTitle>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-muted-foreground">
                  <li>• Estratégias de alimentação sem restrição</li>
                  <li>• Como montar pratos equilibrados</li>
                  <li>• Receitas práticas e deliciosas</li>
                  <li>• Planejamento de refeições eficiente</li>
                </ul>
              </CardContent>
            </Card>
                            <ul className="space-y-2 text-muted-foreground">
                  <li>• Exercícios que cabem na sua rotina</li>
                  <li>• Treinos de 15-30 minutos eficazes</li>
                  <li>• Como acelerar o metabolismo naturalmente</li>
                  <li>• Atividades para cada tipo de pessoa</li>
                </ul>
              </CardContent>
            </Card>
            <Card className="bg-background">
              <CardHeader>
                <img 
                  src="https://placeholder-image-service.onrender.com/image/400x200?prompt=Peaceful meditation scene with journal and healthy lifestyle elements representing emotional balance&id=c5743415-f204-4685-bf53-cadc5daad77d&customer_id=cus_T37mvv9upb5WPT"
                  alt="Cena de meditação pacífica com diário e elementos de estilo de vida saudável representando equilíbrio emocional"
                  className="w-full rounded-lg mb-4"
                />
                <CardTitle className="text-primary">Módulo 4: Equilíbrio Emocional</CardTitle>
              </CardHeader>
              <CardContent>
                <ul className="space-y-2 text-muted-foreground">
                  <li>• Como lidar com a ansiedade alimentar</li>
                  <li>• Técnicas de controle emocional</li>
                  <li>• Estratégias para situações desafiadoras</li>
                  <li>• Construir autoestima e confiança</li>
                </ul>
              </CardContent>
            </Card>
          </div>
        </div>
      </section>
      {/* Depoimentos */}
      <section className="py-20">
        <div className="max-w-6xl mx-auto px-4">
          <h3 className="text-3xl font-bold text-center mb-12">
            Veja os resultados de quem já transformou sua vida
          </h3>

                      <Card className="bg-background">
              <CardHeader>
                <div className="flex items-center gap-4">
                  <img 
                    src="https://placeholder-image-service.onrender.com/image/80x80?prompt=Joyful woman with dark hair celebrating healthy lifestyle transformation with bright smile&id=c5743415-f204-4685-bf53-cadc5daad77d&customer_id=cus_T37mvv9upb5WPT"
                    alt="Mulher alegre com cabelo escuro celebrando transformação de estilo de vida saudável com sorriso brilhante"
                    className="w-16 h-16 rounded-full object-cover"
                  />
                  <div>
                    <CardTitle className="text-base">Carla Santos</CardTitle>
                    <p className="text-sm text-muted-foreground">Perdeu 18kg em 5 meses</p>
                  </div>
                </div>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  "Depois de tantas dietas frustradas, o Recomeço Real me ensinou que 
                  emagrecer pode ser prazeroso. Recomendo para todas as minhas amigas!"
                </p>
                <div className="text-primary mt-2">⭐⭐⭐⭐⭐</div>
              </CardContent>
            </Card>
          </div>
        </div>
      </section>
      {/* Garantia */}
      <section className="py-20 bg-secondary/10">
        <div className="max-w-4xl mx-auto px-4 text-center">
          <img 
            src="https://placeholder-image-service.onrender.com/image/150x150?prompt=30 day money back guarantee badge with shield and checkmark in green and gold colors&id=c5743415-f204-4685-bf53-cadc5daad77d&customer_id=cus_T37mvv9upb5WPT"
            alt="Selo de garantia de devolução do dinheiro de 30 dias com escudo e marca de verificação em cores verde e dourado"
            className="w-32 h-32 mx-auto mb-8"
          />
          
          <h3 className="text-3xl font-bold mb-6">
            Garantia Incondicional de 30 Dias
          </h3>
          
          <p className="text-xl text-muted-foreground mb-8">
            Experimente o <strong>Recomeço Real</strong> por 30 dias. Se não ficar 100% satisfeita, 
            devolvemos todo o seu dinheiro. Sem perguntas, sem burocracia.
          </p>
          
          <p className="text-lg font-semibold text-primary">
            Você não tem nada a perder, apenas peso!
          </p>
        </div>
      </section>

      {/* Preço e CTA */}
      <section id="comprar" className="py-20 bg-gradient-to-br from-primary/10 to-secondary/10">
        <div className="max-w-4xl mx-auto px-4 text-center">
          <h3 className="text-3xl font-bold mb-8">
            Sua Transformação Completa Por Apenas:
          </h3>
          
          <Card className="bg-background max-w-lg mx-auto border-2 border-primary/20">
            <CardHeader>
              <div className="text-center">
                <p className="text-muted-foreground line-through text-xl">De R$ 297,00</p>
                <CardTitle className="text-5xl font-bold text-primary mb-2">R$ 67,90</CardTitle>
                <p className="text-muted-foreground">Pagamento único • Acesso vitalício</p>
              </div>
            </CardHeader>
            <CardContent className="space-y-6">
              <div className="text-left space-y-3">
                <div className="flex items-center gap-2">
                  <span className="text-primary">✅</span>
                  <span>4 Módulos Completos de Transformação</span>
                </div>
                <div className="flex items-center gap-2">
                  <span className="text-primary">✅</span>
                  <span>Material em Vídeo + PDF Complementar</span>
                </div>
                <div className="flex items-center gap-2">
                  <span className="text-primary">✅</span>
                  <span>Acesso Vitalício ao Conteúdo</span>
                </div>
                <div className="flex items-center gap-2">
                  <span className="text-primary">✅</span>
                  <span>Garantia de 30 Dias</span>
                                  </div>
              </div>
              
              <div className="bg-destructive/10 border border-destructive/20 rounded-lg p-4">
                <p className="text-destructive font-semibold mb-2">🔥 ÚLTIMAS VAGAS</p>
                <p className="text-sm text-muted-foreground">
                  Esta oferta especial termina em breve. Não perca a chance de transformar sua vida!
                </p>
              </div>
              
              <Button 
                size="lg" 
                className="w-full text-xl py-6 bg-primary hover:bg-primary/90"
              >
                GARANTIR MINHA VAGA AGORA
              </Button>
              
              <div className="flex justify-center items-center gap-4 text-sm text-muted-foreground">
                <img 
                  src="https://placeholder-image-service.onrender.com/image/120x40?prompt=SSL secure payment badge with padlock icon and checkmark&id=c5743415-f204-4685-bf53-cadc5daad77d&customer_id=cus_T37mvv9upb5WPT"
                  alt="Selo de pagamento seguro SSL com ícone de cadeado e marca de verificação"
                  className="h-8"
                />
                <span>Pagamento 100% Seguro</span>
              </div>
            </CardContent>
          </Card>
        </div>
      </section>
      {/* FAQ */}
      <section className="py-20">
        <div className="max-w-4xl mx-auto px-4">
          <h3 className="text-3xl font-bold text-center mb-12">
            Perguntas Frequentes
          </h3>
          <div className="space-y-6">
            <Card>
              <CardHeader>
                <CardTitle>Como funciona o curso?</CardTitle>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  O curso é 100% online e você recebe acesso imediato após a compra. 
                  São 4 módulos com vídeo-aulas práticas que você pode assistir no seu próprio ritmo.
                </p>
              </CardContent>
            </Card>
            <Card>
              <CardHeader>
                <CardTitle>Por quanto tempo tenho acesso?</CardTitle>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  O acesso é vitalício! Você pode assistir quantas vezes quiser, quando quiser.
                </p>
              </CardContent>
            </Card>
<Card>
              <CardHeader>
                <CardTitle>E se eu não gostar do curso?</CardTitle>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  Oferecemos garantia incondicional de 30 dias. Se não ficar satisfeita, 
                  devolvemos 100% do seu dinheiro.
                </p>
              </CardContent>
            </Card>
            <Card>
              <CardHeader>
                <CardTitle>O método funciona para qualquer idade?</CardTitle>
              </CardHeader>
              <CardContent>
                <p className="text-muted-foreground">
                  Sim! O Recomeço Real é baseado em princípios universais que funcionam 
                  para qualquer pessoa, independente da idade.
                </p>
              </CardContent>
            </Card>
          </div>
        </div>
      </section>

      {/* Footer CTA */}
      <section className="py-20 bg-primary text-primary-foreground text-center">
        <div className="max-w-4xl mx-auto px-4">
          <h3 className="text-3xl font-bold mb-6">
            Não deixe para amanhã a transformação que você pode começar hoje!
          </h3>
          
          <p className="text-xl opacity-90 mb-8">
            Milhares de mulheres já transformaram suas vidas. Você será a próxima?
          </p>
          
          <Button 
            size="lg" 
            variant="secondary"
            className="text-xl px-12 py-6"
            onClick={() => scrollToSection('comprar')}
          >
            SIM, QUERO ME TRANSFORMAR AGORA!
          </Button>
        </div>
      </section>
      {/* Footer */}
      <footer className="bg-muted py-12">
        <div className="max-w-6xl mx-auto px-4 text-center">
          <p className="text-muted-foreground">
            © 2024 Recomeço Real - Todos os direitos reservados
          </p>
          <p className="text-sm text-muted-foreground mt-2">
            Este produto não substitui o acompanhamento médico. Consulte sempre um profissional de saúde.
          </p>
        </div>
      </footer>
      </div>
  );
};
export default LandingPageEmagrecimento;
