import discord
from discord.ext import commands
import random

intents = discord.Intents.default()
intents.message_content = True
bot = commands.Bot(command_prefix='$', intents=intents)

@bot.event
async def on_ready():
    print(f'Bot Eco-Informativo logado como {bot.user}')


@bot.command()
async def fato(ctx):
    fatos = [
        "Você sabia? O plástico pode levar de 400 a 1000 anos para se decompor na natureza. 🌍⏳",
        "Carros elétricos não emitem gases no escapamento, mas a mineração para a produção de suas baterias ainda gera impactos ambientais que precisam ser solucionados. 🔋⛏️",
        "Foguetes modernos liberam na atmosfera fuligem, alumina e outros compostos que podem afetar a camada de ozônio. O progresso tem seu preço! 🚀☁️"
    ]
    await ctx.send(f"📖 **Fato Ambiental:**\n{random.choice(fatos)}")

@bot.command()
async def avancado(ctx):
    await ctx.send("🌱 **Prática Avançada:** Já pensou em ter uma composteira? Ela transforma resíduos orgânicos (cascas de frutas e legumes) em adubo rico, reduzindo o lixo dos aterros em até 50%!")

bot.run("TOKEN")
