{spawn}     = require 'child_process'
{watchTree} = require 'watch'
_           = require 'underscore'

task 'dev', 'rebuild the project', (options) ->
  spawn 'coffee', ['--output', 'lib/src',  '--watch', '--compile', 'src'],  stdio: 'inherit'
  spawn 'coffee', ['--output', 'lib/test', '--watch', '--compile', 'test'], stdio: 'inherit'

  watchTree 'lib', =>
    spawn 'npm', ['test'], stdio: 'inherit'
