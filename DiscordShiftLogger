import discord
from discord.ext.commands import Bot
from discord.ext import commands
import asyncio
import datetime
import csv

timestamp = datetime.datetime.now()

with open('FILENAMEHERE.csv', 'w', newline='') as csv_file:
	fields = ['Event', 'User', 'Time','Day']
	writer = csv.writer(csv_file)
	writer.writerow(fields)

Client = discord.Client()
client = commands.Bot(command_prefix = ["!"])
bot_token = "[PUT YOUR DISCORD SERVER BOT TOKEN HERE]"

@client.event
async def on_ready():
	print("Bot is ready!")
	print("Logged as: " + client.user.name)
	print("ID: " + str(client.user.id))
	for guild in client.guilds:
		print ("Bot connected to server: {}".format(guild))
	print("------")


## From here on, the bot is listening to commands (prefix = !) and adding them to the csv file

@client.command()
async def shift(ctx):
	name = ctx.message.author.name
	start = datetime.datetime.now().time()
	date = datetime.datetime.now().date()
	shift_start = ["shift start",name, start, date]
	with open('FILENAMEHERE.csv', 'a') as output:
		writer = csv.writer(output)
		writer.writerow(shift_start)
	await ctx.send("Hi, " + str(ctx.message.author.mention) + "! Thanks for letting me know. Your shift has started.")
	print(ctx.message.author.name,"used the bot at",timestamp)

@client.command()
async def pause(ctx):
	name = ctx.message.author.name
	start = datetime.datetime.now().time()
	day = datetime.datetime.now().date()
	pause_start = ["pause start",name, start, day]
	with open('FILENAMEHERE.csv', 'a') as output:
		writer = csv.writer(output)
		writer.writerow(pausa_start)
	await ctx.send("Let's log your pause, " + str(ctx.message.author.mention) + "! :)")
	print(ctx.message.author.name,"used the bot at",timestamp)

@client.command()
async def back(ctx):
	name = ctx.message.author.name
	start = datetime.datetime.now().time()
	day = datetime.datetime.now().date()
	pause_end = ["pause end", name, start, day]
	with open('FILENAMEHERE.csv', 'a') as output:
		writer = csv.writer(output)
		writer.writerow(pause_end)
	await ctx.send("Ok, " + str(ctx.message.author.mention) + ". I just logged your return.")
	print(ctx.message.author.name,"used the bot at",timestamp)
	
@client.command()
async def finish(ctx):
	name = ctx.message.author.name
	start = datetime.datetime.now().time()
	day = datetime.datetime.now().date()
	shift_end = ["shift finish", name, start, day]
	with open('FILENAMEHERE.csv', 'a') as output:
		writer = csv.writer(output)
		writer.writerow(shift_end)
	await ctx.send(str(ctx.message.author.mention) + " your shift ended and I logged it. Thanks!")
	print(ctx.message.author.name,"used the bot at",timestamp)
    
client.run(bot_token)
