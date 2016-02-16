require_relative '../plugin'

class Chatbot::Holo
  include Chatbot::Plugin

  match /^Rainbow Bot, I love you/, :use_prefix => false
  match /^Rainbow Bot, kill/, :use_prefix => false, :method => :poor_cod4
  match /^\/me gives Rainbow Quartz Bot an apple/, :use_prefix => false, :method => :apple

  # @param [User] user
  def execute(user)
    if user.name.eql? 'Opal'
      @client.send_msg '/me hugs Opal'
      @client.send_msg 'I love you too <3'
    else
      @client.send_msg "#{user.name}: Holo the Wise Wolf does not associate with such filth"
    end
  end

  # @param [User] user
  def poor_cod4(user)
    if user.name.eql? 'Opal'
      @client.send_msg '/me breaks Ultimate-Steven-Universe1\'s neck'
      @client.send_msg 'I love you, Opal <3'
    end
  end

  # @param [User] user
  def apple(user)
    if user.name.eql? 'Opal'
      @client.send_msg '/me happily chomps on the apple'
      @client.send_msg 'Thanks sweetie! <3'
    else
      @client.send_msg "/me throws the apple back at #{user.name}, hitting them square in the face"
    end
  end
end
