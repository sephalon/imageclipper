# vim: set filetype=python:

env = DefaultEnvironment()

env.ParseConfig('pkg-config --cflags --libs opencv')
env.Append(LIBS=['boost_system', 'boost_filesystem'])

profile = ARGUMENTS.get('profile', 0)
if int(profile):
    env.Append(CCFLAGS=['-pg'])
    env.Append(LINKFLAGS=['-pg'])

VariantDir('build', 'src', duplicate=0)
Default(env.Program('imageclipper', Glob('build/*.cpp')))
